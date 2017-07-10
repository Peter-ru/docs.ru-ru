---
title: "Привязки и безопасность | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязки [WCF]"
  - "привязки [WCF], безопасность"
  - "безопасность WCF"
  - "Windows Communication Foundation, безопасность"
ms.assetid: 4de03dd3-968a-4e65-af43-516e903d7f95
caps.latest.revision: 42
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 42
---
# Привязки и безопасность
Предоставляемые системой привязки, включенные в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], обеспечивают быстрый способ программирования приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].За одним исключением, во всех привязках включена схема безопасности по умолчанию.Этот раздел поможет выбрать привязку, соответствующую требованиям к безопасности.  
  
 Общие сведения о безопасности в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о программировании в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с использованием привязок см. в разделе [Программирование безопасности WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md).  
  
 Если привязка уже выбрана, дополнительные сведения о связанных с безопасностью поведениях времени выполнения см. в разделе [Поведения безопасности](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
 Некоторые функции безопасности невозможно запрограммировать с помощью привязок, предоставляемых системой.Сведения о дополнительных возможностях, обеспечиваемых пользовательскими привязками, см. в разделе [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).  
  
## Функции безопасности привязок  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит ряд предоставляемых системой привязок, удовлетворяющих большей части потребностей.Если определенная привязка не удовлетворяет всем необходимым требованиям, можно также создать пользовательскую привязку.Список предоставляемых системой привязок см. в разделе [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о пользовательских привязках см. в разделе [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Каждая привязка в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] существует в двух видах: в виде API и в виде элемента XML, используемого в файле конфигурации.Например, для привязки `WSHttpBinding` \(API\) имеется эквивалентный элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 В следующем подразделе перечисляются обе формы каждой из привязок и приводится краткое описание функций безопасности.  
  
### BasicHttp  
 В коде используйте класс <xref:System.ServiceModel.BasicHttpBinding>; в конфигурации используйте элемент [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).  
  
 Эта привязка предназначена для использования с различными существующими технологиями, включая перечисленные ниже.  
  
-   Веб\-службы ASP.NET \(ASMX\), версия 1.  
  
-   Приложения расширений веб\-служб \(WSE\).  
  
-   Базовый профиль Basic Profile, определенный в спецификации взаимодействия веб\-служб WS\-I \([http:\/\/go.microsoft.com\/fwlink\/?LinkId\=38955](http://go.microsoft.com/fwlink/?LinkId=38955)\).  
  
-   Базовый профиль безопасности, определенный в спецификации WS\-I.  
  
 По умолчанию эта привязка не является безопасной.Она предназначена для взаимодействия со службами ASMX.Если безопасность включена, эта привязка обеспечивает беспрепятственное взаимодействие с механизмами безопасности служб IIS, такими как обычная проверка подлинности, дайджест\-проверка и встроенная система безопасности Windows.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).Эта привязка поддерживает следующие функции:  
  
-   Безопасность транспорта HTTPS.  
  
-   Обычная проверка подлинности HTTP.  
  
-   WS\-Security.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.BasicHttpSecurity>, <xref:System.ServiceModel.BasicHttpMessageSecurity>, <xref:System.ServiceModel.BasicHttpMessageCredentialType> и <xref:System.ServiceModel.BasicHttpSecurityMode>.  
  
### WSHttpBinding  
 В коде используйте класс <xref:System.ServiceModel.WSHttpBinding>; в конфигурации используйте элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
 По умолчанию эта привязка реализует спецификацию WS\-Security и обеспечивает взаимодействие со службами, реализующими спецификации WS\-\*.Она поддерживает следующие функции:  
  
-   Безопасность транспорта HTTPS.  
  
-   WS\-Security.  
  
-   Защита транспорта HTTPS с использованием безопасности учетных данных сообщения SOAP для проверки подлинности вызывающей стороны.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.WSHttpSecurity>, <xref:System.ServiceModel.MessageSecurityOverHttp>, <xref:System.ServiceModel.MessageCredentialType>, <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.HttpTransportSecurity>, <xref:System.ServiceModel.HttpClientCredentialType> и <xref:System.ServiceModel.HttpProxyCredentialType>.  
  
### WSDualHttpBinding  
 В коде используйте класс <xref:System.ServiceModel.WSDualHttpBinding>; в конфигурации используйте элемент [\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).  
  
 Эта привязка предназначена для обеспечения приложений дуплексных служб.Эта привязка реализует спецификацию WS\-Security для обеспечения безопасности передачи на основе сообщений.Безопасность транспорта отсутствует.По умолчанию предусмотрены следующие функции.  
  
-   Для надежности реализован обмен сообщениями WS\-Reliable Messaging.  
  
-   Для транспортной безопасности и проверки подлинности реализована спецификация WS\-Security.  
  
-   Для доставки сообщений используется протокол HTTP.  
  
-   Используется кодирование текстовых сообщений\/сообщений XML.  
  
 Используя WS\-Security \(безопасность на уровне сообщений\), эта привязка позволяет настроить следующие параметры:  
  
-   Набор алгоритмов безопасности для определения алгоритма шифрования.  
  
-   Параметры привязки для:  
  
    -   предоставления учетных данных службы, получаемых клиентом по внештатному каналу;  
  
    -   предоставления учетных данных службы, согласованных со службой в процессе настройки канала.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.WSDualHttpSecurity> и <xref:System.ServiceModel.WSDualHttpSecurityMode>.  
  
### NetTcpBinding  
 В коде используйте класс <xref:System.ServiceModel.NetTcpBinding>; в конфигурации используйте элемент [\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).  
  
 Эта привязка оптимизирована для обмена данными между компьютерами.По умолчанию она имеет следующие характеристики:  
  
-   Реализуется безопасность на транспортном уровне.  
  
-   Для безопасности передачи и проверки подлинности используется безопасность Windows.  
  
-   Для транспорта используется протокол TCP.  
  
-   Реализуется кодирование двоичных сообщений.  
  
-   Реализуется обмен сообщениями WS\-Reliable Messaging.  
  
 Дополнительно возможны:  
  
-   Безопасность на уровне сообщений \(с использованием WS\-Security\).  
  
-   Безопасность транспорта с учетными данными сообщений — конфиденциальность и целостность обеспечиваются протоколом TLS через TCP, а учетные данные для проверки подлинности обеспечиваются спецификацией WS\-Security.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.NetTcpSecurity>, <xref:System.ServiceModel.TcpTransportSecurity>, <xref:System.ServiceModel.TcpClientCredentialType>, <xref:System.ServiceModel.MessageSecurityOverTcp> и <xref:System.ServiceModel.MessageCredentialType>.  
  
### NetNamedPipeBinding  
 В коде используйте класс <xref:System.ServiceModel.NetNamedPipeBinding>; в конфигурации используйте элемент [\<netNamedPipeBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md).  
  
 Эта привязка оптимизирована для обмена данными между процессами \(обычно на одном компьютере\).По умолчанию эта привязка имеет следующие характеристики:  
  
-   Для передачи сообщений и проверки подлинности используется безопасность транспорта.  
  
-   Для доставки сообщений используются именованные каналы.  
  
-   Реализуется кодирование двоичных сообщений.  
  
-   Шифрование и подписывание сообщений.  
  
 Дополнительно возможны:  
  
-   Проверка подлинности с использованием безопасности Windows.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.NetNamedPipeSecurity>, <xref:System.ServiceModel.NetNamedPipeSecurityMode> и <xref:System.ServiceModel.NamedPipeTransportSecurity>.  
  
### MsmqIntegrationBinding  
 В коде используйте класс <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>; в конфигурации используйте элемент [\<msmqIntegrationBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).  
  
 Эта привязка оптимизирована для создания клиентов и служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], взаимодействующих с конечными точками MSMQ \(Microsoft Message Queuing\), созданными без использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 По умолчанию в этой привязке используется безопасность транспорта и обеспечиваются следующие характеристики безопасности:  
  
-   Система безопасности может быть отключена \(None\).  
  
-   Безопасность транспорта MSMQ \(Transport\).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] объекты <xref:System.ServiceModel.NetMsmqSecurity> и <xref:System.ServiceModel.NetMsmqSecurityMode>.  
  
### NetMsmqBinding  
 В коде используйте класс <xref:System.ServiceModel.NetMsmqBinding>; в конфигурации используйте элемент [\<netMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).  
  
 Эта привязка предназначена для использования при создании служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которым требуется поддержка очереди сообщений MSMQ.  
  
 По умолчанию в этой привязке используется безопасность транспорта и обеспечиваются следующие характеристики безопасности:  
  
-   Система безопасности может быть отключена \(None\).  
  
-   Безопасность транспорта MSMQ \(Transport\).  
  
-   Безопасность сообщений на основе SOAP \(Message\).  
  
-   Одновременное использование безопасности транспорта и безопасности сообщений \(Both\).  
  
-   Поддерживаемые типы учетных данных клиента: None, Windows, UserName, Certificate, IssuedToken.  
  
 Учетные данные типа <xref:System.ServiceModel.MessageCredentialType> поддерживаются только в том случае, если задан режим безопасности <xref:System.ServiceModel.NetMsmqSecurityMode> или <xref:System.ServiceModel.NetMsmqSecurityMode>.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.MessageSecurityOverMsmq> и <xref:System.ServiceModel.MsmqTransportSecurity>.  
  
### WSFederationHttpBinding  
 В коде используйте класс <xref:System.ServiceModel.WSFederationHttpBinding>; в конфигурации используйте элемент [\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).  
  
 По умолчанию в этой привязке используется спецификация WS\-Security \(безопасность на уровне сообщений\).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Федерация](../../../../docs/framework/wcf/feature-details/federation.md), <xref:System.ServiceModel.WSFederationHttpSecurity> и <xref:System.ServiceModel.WSFederationHttpSecurityMode>.  
  
## Пользовательские привязки  
 Если ни одна из предоставляемых системой привязок не удовлетворяет вашим требованиям, можно создать пользовательскую привязку с пользовательским элементом привязки безопасности.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md).  
  
## Функции привязок  
 В следующей таблице перечислены функции, обеспечиваемые настройкой режима безопасности; другими словами, перечислены доступные функции, если для режима безопасности задано значение `Transport`, `Message` или `TransportWithMessageCredential`.Эта таблица поможет найти функции безопасности, необходимые для вашего приложения.  
  
|Параметр|Функции|  
|--------------|-------------|  
|Транспорт|Проверка подлинности сервера<br /><br /> Проверка подлинности клиента<br /><br /> Безопасность типа "точка\-точка"<br /><br /> Взаимодействие<br /><br /> Аппаратное ускорение<br /><br /> Высокая пропускная способность<br /><br /> Безопасный брандмауэр<br /><br /> Приложения с большой задержкой<br /><br /> Повторное шифрование по нескольким участкам ретрансляции|  
|Сообщение|Проверка подлинности сервера<br /><br /> Проверка подлинности клиента<br /><br /> Сквозная безопасность<br /><br /> Взаимодействие<br /><br /> Утверждения с широкими функциональными возможностями<br /><br /> Федерация<br /><br /> Многофакторная проверка подлинности<br /><br /> Пользовательские маркеры<br /><br /> Служба удостоверения\/отметки времени<br /><br /> Приложения с большой задержкой<br /><br /> Сохраняемость сигнатур сообщений|  
|TransportWithMessageCredential|Проверка подлинности сервера<br /><br /> Проверка подлинности клиента<br /><br /> Безопасность типа "точка\-точка"<br /><br /> Взаимодействие<br /><br /> Аппаратное ускорение<br /><br /> Высокая пропускная способность<br /><br /> Утверждения клиентов с широкими функциональными возможностями<br /><br /> Федерация<br /><br /> Многофакторная проверка подлинности<br /><br /> Пользовательские маркеры<br /><br /> Безопасный брандмауэр<br /><br /> Приложения с большой задержкой<br /><br /> Повторное шифрование по нескольким участкам ретрансляции|  
  
 В следующей таблице перечислены привязки, поддерживающие различные параметры режима.Выберите в таблице привязку для использования при создании конечной точки своей службы.  
  
|Привязка|Поддержка режима Transport|Поддержка режима Message|Поддержка режима TransportWithMessageCredential|  
|--------------|--------------------------------|------------------------------|-----------------------------------------------------|  
|`BasicHttpBinding`|Да|Да|Да|  
|`WSHttpBinding`|Да|Да|Да|  
|`WSDualHttpBinding`|Нет|Да|Нет|  
|`NetTcpBinding`|Да|Да|Да|  
|`NetNamedPipeBinding`|Да|Нет|Нет|  
|`NetMsmqBinding`|Да|Да|Нет|  
|`MsmqIntegrationBinding`|Да|Нет|Нет|  
|`wsFederationHttpBinding`|Нет|Да|Да|  
  
## Учетные данные транспорта в привязках  
 В приведенной ниже таблице перечислены типы учетных данных клиента, доступные при использовании привязки `BasicHttpBinding` или `WSHttpBinding` в режиме безопасности транспорта.  
  
|Тип|Описание|  
|---------|--------------|  
|None|Указывает, что клиенту не требуется предоставлять учетные данные.Это означает, что клиент является анонимным.|  
|Basic|Обычная проверка подлинности.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] в документе "RFC 2617 – HTTP Authentication: Basic and Digest Authentication" \(RFC 2617 – Проверка подлинности HTTP: обычная проверка подлинности и дайджест\-проверка подлинности\) по ссылке [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=84023](http://go.microsoft.com/fwlink/?LinkId=84023).|  
|Digest|Дайджест\-проверка подлинности.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] в документе "RFC 2617 – HTTP Authentication: Basic and Digest Authentication" \(RFC 2617 – Проверка подлинности HTTP: обычная проверка подлинности и дайджест\-проверка подлинности\) по ссылке [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=84023](http://go.microsoft.com/fwlink/?LinkId=84023).|  
|NTLM|Проверка подлинности NTLM \(NT LAN Manager\).|  
|Windows|Проверка подлинности Windows.|  
|Certificate|Проверка подлинности производится с использованием сертификата.|  
|IssuedToken|Позволяет службе потребовать, чтобы проверка подлинности клиента производилась с помощью маркера, выданного службой маркеров безопасности или [!INCLUDE[infocard](../../../../includes/infocard-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
### Учетные данные клиента в привязках в режиме Message  
 В приведенной ниже таблице перечислены типы учетных данных клиента, доступные при использовании привязки в режиме безопасности Message.  
  
|Тип|Описание|  
|---------|--------------|  
|None|Позволяет службе взаимодействовать с анонимными клиентами.|  
|Windows|Позволяет проводить обмен сообщениями SOAP, если выполнена проверка подлинности с помощью учетных данных Windows.|  
|UserName|Позволяет службе запрашивать проверку подлинности клиента на основе учетных данных типа "имя пользователя".Обратите внимание, что если задан режим безопасности `TransportWithMessageCredential`, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает отправку дайджеста пароля или создание ключей с помощью пароля и использование таких ключей для режима безопасности Message.Таким образом, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] принудительно задает безопасность транспорта при использовании учетных данных типа "имя пользователя".|  
|Certificate|Позволяет службе требовать проверку подлинности клиента с помощью сертификата.|  
|IssuedToken|Позволяет службе использовать службу маркеров безопасности для создания пользовательского маркера.|  
  
## См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Защита служб и клиентов](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Выбор типа учетных данных](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [Возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [Поведения безопасности](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x419)