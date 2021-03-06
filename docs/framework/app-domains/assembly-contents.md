---
title: "Содержимое сборок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51380126de164a4e0934068c7e0de55f5f3d92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-contents"></a>Содержимое сборок
В общем случае статическая сборка может состоять из четырех элементов.  
  
-   [Манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md), который содержит метаданные сборки.  
  
-   Метаданные типов.  
  
-   Реализующий типы код на промежуточном языке MSIL.  
  
-   Набор ресурсов.  
  
 Обязательным является лишь манифест сборки, однако остальные типы ресурсов необходимы для обеспечения нужной функциональности сборки.  
  
 Существует несколько способов группировки этих элементов в сборку. Все эти элементы можно объединить в одном физическом файле, как показано на следующей иллюстрации.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")  
Сборка из одного файла  
  
 Или элементы сборки могут находиться в нескольких файлах. Эти файлы могут быть модулями скомпилированного кода (.netmodule), ресурсами (например, файлами BMP или JPG) или иными файлами, необходимыми приложению. Сборка из нескольких файлов создается, если необходимо собрать модули, написанные на различных языках, и оптимизировать загрузку приложения, выделяя редко используемые пользовательские типы в модуль, который будет загружаться только при необходимости.  
  
 На следующем рисунке разработчик гипотетического приложения выделил в отдельный модуль некоторый вспомогательный код, а ресурс большого объема (BMP-рисунок) оставил в первоначальном файле. При использовании .NET Framework загрузка файла выполняется только при ссылке; процесс загрузки кода оптимизируется путем размещения в отдельном файле кода, ссылки на который используются редко.  
  
 ![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")  
Сборка из нескольких файлов  
  
> [!NOTE]
>  Файлы, составляющие такую сборку, не являются физически связанными в файловой системе. Скорее они связываются друг с другом с помощью манифеста сборки, а среда CLR управляет ими как одним целым.  
  
 На этом рисунке все три принадлежащих сборке файла описаны в манифесте сборки, который находится в файле MyAssembly.dll. Для файловой системы они являются тремя различными файлами. Обратите внимание: Util.netmodule был скомпилирован как модуль, поскольку он не содержит данных о сборке. При создании сборки ее манифест был добавлен в файл MyAssembly.dll, чтобы связать сборку с файлами Util.netmodule и Graphic.bmp.  
  
 При проектировании исходного кода необходимо принять определенные решения о способе разделения функций приложения между одним или несколькими файлами. При проектировании кода .NET Framework необходимо принять аналогичные решения о способе разделения функций между одной или несколькими сборками.  
  
## <a name="see-also"></a>См. также  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Манифест сборки](../../../docs/framework/app-domains/assembly-manifest.md)  
 [Вопросы безопасности сборок](../../../docs/framework/app-domains/assembly-security-considerations.md)
