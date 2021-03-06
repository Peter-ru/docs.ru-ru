---
title: "Выбор дополнительного формата"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b14aa97f1483b3c69bfecfa0b625e590c0c37836
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="advanced-format-selection"></a>Выбор дополнительного формата
Данный образец демонстрирует расширение программной модели [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] REST для поддержки новых форматов исходящих ответов. Кроме того, образец использует шаблон T4 для возврата ответов в виде страницы XHTML, показывая, как можно реализовать наглядную программную модель.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Образец состоит из простой службы, а также клиентского кода, производящего запросы к этой службе.  Служба поддерживает единственную операцию [WebGet], имеющую следующую сигнатуру метода: `Message EchoListWithGet(string list);`  
  
 Когда клиент производит запрос к службе, он предоставляет разделенный запятыми список элементов в параметре строки запроса `list`, а служба возвращает тот же список в одном из следующих форматов: XML, JSON, Atom, XHTML или jpeg.  
  
 Формат ответа, возвращаемого службой, определяется, во-первых, параметром строки запроса `format`, а во-вторых, заголовком HTTP Accept, содержащимся в запросе. Если значение параметра строки запроса `format` указывает один из перечисленных ранее форматов, ответ возвращается в этом формате. Если параметр строки запроса `format` отсутствует, служба перебирает элементы заголовка Accept в запросе и возвращает формат первого поддерживаемого ею типа содержимого content-type.  
  
 Возвращаемый тип операции можно игнорировать. Программная модель [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] REST сама по себе поддерживает только форматы ответа XML и JSON, если операция возвращает тип, отличный от <xref:System.ServiceModel.Channels.Message>. Однако, если используется тип ответа <xref:System.ServiceModel.Channels.Message>, разработчик имеет полный контроль над тем, какой формат должно иметь это сообщение.  
  
 Образец использует методы <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> и <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> для сериализации списка строк в сообщениях XML, JSON и ATOM соответственно. В случае формата ответа jpeg используется метод <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A>, а изображение сохраняется в потоке. Ответ XHTML использует метод <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A>, а также предварительно обработанный шаблон T4, который состоит из TT-файла и автоматически формируемого файла CS. TT-файл позволяет разработчику записывать ответ в виде шаблона, содержащего переменные и управляющие структуры. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]T4 см. в разделе [Создание артефактов с помощью текстовых шаблонов](http://go.microsoft.com/fwlink/?LinkId=166023).  
  
 Образец состоит из резидентной службы и клиента, который работает в консольном приложении. Во время выполнения консольного приложения клиент совершает запросы к службе и выводит в окно консоли нужные сведения из ответов.  
  
#### <a name="to-run-this-sample"></a>Запуск образца  
  
1.  Откройте решение образца «Advanced Format Selection». Для успешного выполнения образца среду [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо запускать от имени администратора. Для этого щелкните правой кнопкой мыши [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] значок и выбрав **Запуск от имени администратора** в контекстном меню.  
  
2.  Нажмите сочетание клавиш CTRL+SHIFT+B для построения решения, затем сочетание клавиш Ctrl-F5 для запуска консольного приложения проекта AdvancedFormatSelection без отладки. Открывается окно консоли с URI запущенной службы и URI HTML-страницы справки для запущенной службы.  
  
3.  Во время выполнения образца клиент отправляет запросы к службе и выводит ответы в окно консоли. Обратите внимание на различные форматы ответов: XML, JSON, Atom и XHTML.  
  
4.  После этого вам будет предложено перейти к URI, в котором можно запросить ответ в формате JPEG. Откройте браузер и перейдите по заданному URI.  
  
5.  Чтобы завершить образец, нажмите любую клавишу.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## <a name="see-also"></a>См. также
