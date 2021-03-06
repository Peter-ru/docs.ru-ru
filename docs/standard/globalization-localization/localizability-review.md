---
title: "Обзор локализуемости"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- world-ready applications, localizability
- application development [.NET Framework], localization
- localizability [.NET Framework]
- international applications [.NET Framework], localizability
- globalization [.NET Framework], localizability
- culture, localizability
- localization [.NET Framework], localizability
- global applications, localizability
- localizing resources
ms.assetid: 3aee2fbb-de47-4e37-8fe4-ddebb9719247
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7633c7fe9e99bde96ee108460e983eff48f1c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="localizability-review"></a>Обзор локализуемости
Проверка локализуемости — промежуточный шаг в разработке международных приложений. Это проверка, что международное приложение готово к локализации, которая позволяет определить код и элементы пользовательского интерфейса, требующие специальной обработки. Этот шаг также помогает удостовериться, что процесс локализации не внесет в приложение функциональных дефектов. Когда все проблемы, выявленные при анализе локализуемости, устранены, приложение готово для локализации. Исчерпывающая проверка локализуемости позволяет не изменять исходный код при локализации.  
  
 Проверка локализуемости состоит из трех следующих проверок.  
  
-   [Рекомендации по глобализации реализуются?](#global)  
  
-   [Язык и региональные параметры функции обрабатываются правильно?](#culture)  
  
-   [Проводилось ли тестирование приложения с международными данными?](#test)  
  
<a name="global"></a>   
## <a name="implementing-globalization-recommendations"></a>Реализация рекомендаций по глобализации  
 Если конструирования и разработки приложения помнить о локализации, а если выполнены рекомендации обсуждается в [глобализации](../../../docs/standard/globalization-localization/globalization.md) статья локализуемости во многом будет гарантировать качественную локализацию . В противном случае во время этого этапа необходимо проверить и реализовать рекомендации по [глобализации](../../../docs/standard/globalization-localization/globalization.md)и исправить ошибки в исходном коде, которые будут мешать локализации.  
  
<a name="culture"></a>   
## <a name="handling-culture-sensitive-features"></a>Обработка возможностей, чувствительных к языковым и региональным параметрам  
 Платформа .NET Framework не обеспечивает программную поддержку в нескольких областях, которые значительно отличаются в зависимости от языка и региональных параметров. В большинстве случаев для обработки следующих функциональных областей необходимо писать собственный код.  
  
-   Адреса.  
  
-   Телефонные номера.  
  
-   Размеры бумаги.  
  
-   Единицы измерения длины, веса, площади, объема и температуры. Хотя в платформе .NET Framework нет встроенной поддержки преобразования единиц измерения, можно использовать свойство <xref:System.Globalization.RegionInfo.IsMetric%2A?displayProperty=nameWithType>, чтобы определить, использует ли определенная страна или регион метрическую систему, как показано в следующем примере.  
  
     [!code-csharp[Conceptual.Localizability#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.localizability/cs/ismetric1.cs#1)]
     [!code-vb[Conceptual.Localizability#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.localizability/vb/ismetric1.vb#1)]  
  
<a name="test"></a>   
## <a name="testing-your-application"></a>Тестирование приложения  
 Перед локализацией приложения необходимо протестировать его с использованием данных на других языках в международных версиях операционной системы. Хотя большая часть пользовательского интерфейса еще не локализована, можно будет обнаружить различные проблемы, например следующие.  
  
-   Сериализованные данные, которые неправильно десериализуются в разных версиях операционной системы.  
  
-   Числовые данные, которые не соответствуют правилам текущих языка и региональных параметров. Например, числа могут отображаться с неверными разделителями групп, десятичными разделителями или обозначениями денежных единиц.  
  
-   Сведения о дате и времени, которые не соответствуют правилам текущих языка и региональных параметров. Например, числа, представляющие месяц и день, могут следовать в неверном порядке, могут быть неправильными разделители компонентов даты или данные часового пояса.  
  
-   Ресурсы, которые не удается найти, поскольку для приложения не заданы язык и региональные параметры по умолчанию.  
  
-   Строки, которые отображаются в нестандартном порядке для определенных языка и региональных параметров.  
  
-   Сравнения строк или сравнения на равенство, возвращающие непредвиденные результаты.  
  
 Если вы определили при разработке приложения, а затем рекомендации по глобализации, обрабатываются правильно, язык и региональные параметры функций и и разрешения локализации проблем, возникших во время тестирования, можете перейти к следующему шагу [Локализации](../../../docs/standard/globalization-localization/localization.md).  
  
## <a name="see-also"></a>См. также  
 [Глобализация и локализация](../../../docs/standard/globalization-localization/index.md)  
 [Локализация](../../../docs/standard/globalization-localization/localization.md)  
 [Глобализация](../../../docs/standard/globalization-localization/globalization.md)  
 [Ресурсы в приложениях для настольных систем](../../../docs/framework/resources/index.md)
