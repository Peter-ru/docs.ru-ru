---
title: "Как сравнивать утверждения | Microsoft Docs"
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
  - "утверждения [WCF]"
  - "утверждения [WCF], сравнение"
ms.assetid: 0c4ec84d-53df-408f-8953-9bc437f56c28
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Как сравнивать утверждения
Инфраструктура модели удостоверения в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] используется для выполнения проверки авторизации.По существу общей задачей является сравнение утверждений в контексте авторизации с утверждениями, необходимыми для выполнения затребованного действия или доступа к затребованному ресурсу.В этом разделе описывается сравнение утверждений, включая встроенные и пользовательские типы утверждений.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о инфраструктуре модели удостоверений см. в разделе [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).  
  
 При сравнении утверждений сравниваются три элемента одного утверждения \(тип, право и ресурс\) с аналогичными элементами другого утверждения, чтобы определить, одинаковы ли они.См. следующий пример.  
  
 [!code-csharp[c_CustomClaimComparison#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#9)]
 [!code-vb[c_CustomClaimComparison#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#9)]  
  
 Оба утверждения будут иметь тип имени <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, право свойства <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и ресурс строки «someone».Поскольку все три элемента утверждения одинаковы, сами утверждения одинаковы.  
  
 Встроенные типы утверждений сравниваются с помощью метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.При необходимости используется код сравнения, зависящий от утверждений.Например, пусть заданы следующие два утверждения с именем участника\-пользователя:  
  
 [!code-csharp[c_CustomClaimComparison#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#4)]
 [!code-vb[c_CustomClaimComparison#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#4)]  
  
 Код сравнения в методе <xref:System.IdentityModel.Claims.Claim.Equals%2A> возвращает значение `true`, если `example\someone` идентифицирует того же пользователя домена, что и "someone@example.com".  
  
 Пользовательские типы утверждений также могут сравниваться с помощью метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.Однако в тех случаях, когда тип, возвращенный свойством <xref:System.IdentityModel.Claims.Claim.Resource%2A> утверждения, несколько отличается от типа\-примитива, метод <xref:System.IdentityModel.Claims.Claim.Equals%2A> возвращает значение `true`, только если значения, возвращенные свойствами `Resource`, одинаковы для каждого метода <xref:System.IdentityModel.Claims.Claim.Equals%2A>.В других случаях пользовательский тип, возвращенный свойством `Resource`, должен переопределить методы <xref:System.IdentityModel.Claims.Claim.Equals%2A> и <xref:System.Object.GetHashCode%2A>, чтобы выполнить любую необходимую пользовательскую обработку.  
  
### Сравнение встроенных утверждений  
  
1.  Пусть заданы два экземпляра класса <xref:System.IdentityModel.Claims.Claim>. Используйте метод <xref:System.IdentityModel.Claims.Claim.Equals%2A> для выполнения сравнения, как показано в следующем коде.  
  
     [!code-csharp[c_CustomClaimComparison#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#5)]
     [!code-vb[c_CustomClaimComparison#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#5)]  
  
### Сравнение пользовательских утверждений с типами\-примитивами ресурсов  
  
1.  Для пользовательских утверждений с типами\-примитивами ресурсов сравнение может выполняться аналогично сравнению для встроенных утверждений, как показано в следующем коде.  
  
     [!code-csharp[c_CustomClaimComparison#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#6)]
     [!code-vb[c_CustomClaimComparison#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#6)]  
  
2.  Для пользовательских утверждений с типами ресурсов на основе структур или классов тип ресурса должен переопределить метод <xref:System.IdentityModel.Claims.Claim.Equals%2A>.  
  
3.  Сначала проверьте, имеет ли параметр `obj` значение `null`. Если да, верните значение `false`.  
  
     [!code-csharp[c_CustomClaimComparison#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#7)]
     [!code-vb[c_CustomClaimComparison#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#7)]  
  
4.  Затем вызовите метод <xref:System.Object.ReferenceEquals%2A> и передайте `this` и `obj` в качестве параметров.Если этот метод возвращает значение `true`, верните значение `true`.  
  
     [!code-csharp[c_CustomClaimComparison#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#8)]
     [!code-vb[c_CustomClaimComparison#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#8)]  
  
5.  Затем попытайтесь присвоить значение `obj` локальной переменной типа класса.Если эта попытка завершается неуспешно, ссылка имеет значение `null`.В этом случае верните значение `false`.  
  
6.  Выполните пользовательское сравнение, необходимое для правильного сравнения текущего утверждения с предоставленным утверждением.  
  
## Пример  
 В следующем примере показано сравнение пользовательских утверждений, где ресурсом утверждения является тип, отличный от типа\-примитива.  
  
 [!code-csharp[c_CustomClaimComparison#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customclaimcomparison/cs/c_customclaimcomparison.cs#0)]
 [!code-vb[c_CustomClaimComparison#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customclaimcomparison/vb/source.vb#0)]  
  
## См. также  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)   
 [Практическое руководство. Создание пользовательского утверждения](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)