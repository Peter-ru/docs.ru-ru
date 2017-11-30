---
title: "Интерфейс IGCHost2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost2
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost2
helpviewer_keywords: IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c6706696e3fd5158d2b49a4d114d978a26510b67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="igchost2-interface"></a><span data-ttu-id="5884f-102">Интерфейс IGCHost2</span><span class="sxs-lookup"><span data-stu-id="5884f-102">IGCHost2 Interface</span></span>
<span data-ttu-id="5884f-103">Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="5884f-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5884f-104">Для разработки новых приложений рекомендуется использовать [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5884f-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5884f-105">Методы</span><span class="sxs-lookup"><span data-stu-id="5884f-105">Methods</span></span>  
  
|<span data-ttu-id="5884f-106">Метод</span><span class="sxs-lookup"><span data-stu-id="5884f-106">Method</span></span>|<span data-ttu-id="5884f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5884f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5884f-108">Метод SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="5884f-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="5884f-109">Задает размер сегмента и максимальный размер для поколения 0.</span><span class="sxs-lookup"><span data-stu-id="5884f-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="5884f-110">Позволяет поколения 0 и больше размера сегментов `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="5884f-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5884f-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5884f-111">Requirements</span></span>  
 <span data-ttu-id="5884f-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5884f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5884f-113">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5884f-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5884f-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5884f-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5884f-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5884f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5884f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5884f-116">See Also</span></span>  
 [<span data-ttu-id="5884f-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5884f-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5884f-118">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="5884f-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="5884f-119">Компонентный класс CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5884f-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)