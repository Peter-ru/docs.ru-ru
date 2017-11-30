---
title: "Функция LoadFromHistory (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cdb68700ab0c11bbd6b09b83a826dc5ca4faa086
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="5abdc-102">Функция LoadFromHistory (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="5abdc-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="5abdc-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="5abdc-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="5abdc-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="5abdc-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5abdc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5abdc-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5abdc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5abdc-106">Parameters</span></span>  
 <span data-ttu-id="5abdc-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="5abdc-107">pHistoryStream</span></span>  
 <span data-ttu-id="5abdc-108">Указатель на поток данных журнала.</span><span class="sxs-lookup"><span data-stu-id="5abdc-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="5abdc-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="5abdc-109">pBindCtx</span></span>  
 <span data-ttu-id="5abdc-110">Указатель на контекст привязки.</span><span class="sxs-lookup"><span data-stu-id="5abdc-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5abdc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5abdc-111">Requirements</span></span>  
 <span data-ttu-id="5abdc-112">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5abdc-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5abdc-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="5abdc-113">**DLL:**</span></span>  
  
 <span data-ttu-id="5abdc-114">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="5abdc-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="5abdc-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="5abdc-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="5abdc-116">**Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5abdc-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abdc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5abdc-117">See Also</span></span>  
 [<span data-ttu-id="5abdc-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="5abdc-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)