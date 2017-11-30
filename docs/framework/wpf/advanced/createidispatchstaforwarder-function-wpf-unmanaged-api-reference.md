---
title: "Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63195ce2a47add2606f528b18d0d1d58ab0d968c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="9a26f-102">Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="9a26f-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="9a26f-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="9a26f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="9a26f-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоком и windows.</span><span class="sxs-lookup"><span data-stu-id="9a26f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a26f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a26f-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a26f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a26f-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9a26f-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a26f-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="9a26f-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="9a26f-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="9a26f-109">Указатель на `IDispatch` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a26f-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="9a26f-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="9a26f-110">ppForwarder</span></span>  
 <span data-ttu-id="9a26f-111">Указатель на адрес `IDispatch` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a26f-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a26f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9a26f-112">Requirements</span></span>  
 <span data-ttu-id="9a26f-113">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a26f-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a26f-114">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="9a26f-114">**DLL:**</span></span>  
  
 <span data-ttu-id="9a26f-115">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="9a26f-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="9a26f-116">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="9a26f-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="9a26f-117">**Версия платформы .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a26f-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a26f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9a26f-118">See Also</span></span>  
 [<span data-ttu-id="9a26f-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="9a26f-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)