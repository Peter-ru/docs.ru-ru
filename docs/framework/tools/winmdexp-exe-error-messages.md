---
title: "Сообщений об ошибках Winmdexp.exe | Документация Microsoft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WME1095
- WME1110
- WME15
- WME1094
- WME1078
- WME1080
- WME1014
- WME1025
- WME1089
- WME1111
- WME1010
- WME1013
- WME1055
- WME1005
- WME1033
- WME1003
- WME1011
- WME1046
- WME0013
- WME1032
- WME1029
- WME1048
- WME1019
- WME1106
- WME0012
- WME1017
- WME1098
- WME1039
- WME20
- WME1006
- WME1088
- WME0004
- WME10
- WME12
- WME0015
- WME0017
- WME1026
- WME1045
- WME1002
- WME1051
- WME1107
- WME1100
- WME1072
- WME1090
- WME1105
- WME1022
- WME11
- WME17
- WME1063
- WME1041
- WME1057
- WME1037
- WME1007
- WME3
- WME1096
- WME0003
- WME0006
- WME1065
- WME1102
- WME1070
- WME1113
- WME1064
- WME1061
- WME1066
- WME1018
- WME1049
- WME1027
- WME1101
- WME1058
- WME0005
- WME1083
- WME1004
- WME1073
- WME1087
- WME1077
- WME19
- WME1086
- WME1085
- WME1040
- WME8
- WME1081
- WME1023
- WME4
- WME1050
- WME7
- WME1091
- WME14
- WME0007
- WME1024
- WME1012
- WME1036
- WME0010
- WME1104
- WME1035
- WME1021
- WME1075
- WME5
- WME13
- WME1074
- WME1028
- WME0014
- WME1030
- WME1008
- WME1052
- WME1079
- WME1054
- WME1093
- WME1042
- WME2
- WME1062
- WME6
- WME1001
- WME0011
- WME16
- WME0001
- WME1020
- WME1084
- WME1103
- WME1092
- WME1
- WME0002
- WME1112
- WME1016
- WME1060
- WME0008
- WME0016
- WME1097
- WME1034
- WME1108
- WME1082
- WME1099
- WME1069
- WME1031
- WME1009
- WME1068
- WME1067
- WME1059
- WME18
- WME1038
- WME0009
- WME1109
- WME1056
- WME1076
- WME1071
- WME1044
- WME1043
- WME1053
- WME1015
- WME1047
- WME9
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Winmdexp.exe, error messages
- Windows Runtime Metadata Export Tool, error messages
- error messages, Winmdexp.exe
ms.assetid: 8271973c-deba-47a6-8e5e-04ce63f146ad
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62745b203ec5c9db121c3c84578f16ba9c35738d
ms.contentlocale: ru-ru
ms.lasthandoff: 06/02/2017

---
# <a name="winmdexpexe-error-messages"></a>Сообщения об ошибках Winmdexp.exe
Процесс сборки вызывает программу [Winmdexp.exe (средство экспорта метаданных среды выполнения Windows)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md) при использовании шаблона **[!INCLUDE[wrt](../../../includes/wrt-md.md)] Компонент** в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], поэтому сообщения об ошибках Winmdexp.exe отображаются в **Списке ошибок**. Программа Winmdexp.exe работает в модуле, который компилируется с параметром `/target:winmdobj`. Поскольку в качестве входных данных этой программе требуется скомпилированный модуль, в случае сбоя компиляции сообщения об ошибках Winmdexp.exe не отображаются.  
  
 Сообщения об ошибках предназначены для размещения в них всех сведений, необходимых для диагностики состояний ошибок, о которых они сообщают. Но для решения некоторых проблем требуется больше информации, чем может содержать сообщение. Дополнительные сведения см. в статье [Диагностика состояний ошибки компонентов среды выполнения Windows](http://go.microsoft.com/fwlink/p/?LinkId=251127) в Центре разработки для Windows.  
  
 Если ваша ошибка в этой статье не рассматривается и вам кажется, что сообщение об ошибке не содержит всей необходимой информации для решения проблемы, сообщите нам об этом, используя приведенную в статье ссылку. Кроме того, вы можете зарегистрировать ошибку на [веб-сайте Microsoft Connect](http://go.microsoft.com/fwlink/p/?LinkId=251130). Также можно найти дополнительные сведения на [форумах Майкрософт](http://go.microsoft.com/fwlink/p/?LinkId=251129).  
  
## <a name="see-also"></a>См. также  
 [Winmdexp.exe (средство экспорта метаданных среды выполнения Windows)](../../../docs/framework/tools/winmdexp-exe-windows-runtime-metadata-export-tool.md)   
 [Диагностика состояний ошибки компонентов среды выполнения Windows](http://go.microsoft.com/fwlink/p/?LinkId=251127)