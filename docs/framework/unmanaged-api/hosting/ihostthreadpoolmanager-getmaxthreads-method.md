---
title: "Метод IHostThreadPoolManager::GetMaxThreads"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd15b1448c23785437b3dc62562b5d96abb3601c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a><span data-ttu-id="67218-102">Метод IHostThreadPoolManager::GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="67218-102">IHostThreadPoolManager::GetMaxThreads Method</span></span>
<span data-ttu-id="67218-103">Возвращает максимальное число потоков, поддерживаемых основным приложением одновременно в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="67218-103">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67218-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67218-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67218-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67218-105">Parameters</span></span>  
 `pdwMaxWorkerThreads`  
 <span data-ttu-id="67218-106">[out] Указатель на максимальное число потоков, поддерживаемых основным приложением в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="67218-106">[out] A pointer to the maximum number of threads that the host maintains in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67218-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67218-107">Return Value</span></span>  
  
|<span data-ttu-id="67218-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67218-108">HRESULT</span></span>|<span data-ttu-id="67218-109">Описание</span><span class="sxs-lookup"><span data-stu-id="67218-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67218-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67218-110">S_OK</span></span>|<span data-ttu-id="67218-111">`GetMaxThreads`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="67218-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="67218-112">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="67218-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="67218-113">Общеязыковая среда выполнения (CLR (не была загружена в процесс или находится в состоянии, в котором она не удается запустить процесс вызова или неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="67218-113">The common language runtime (CLR( has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="67218-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="67218-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="67218-115">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="67218-115">The call timed out.</span></span>|  
|<span data-ttu-id="67218-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="67218-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="67218-117">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="67218-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="67218-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="67218-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="67218-119">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="67218-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="67218-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="67218-120">E_FAIL</span></span>|<span data-ttu-id="67218-121">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="67218-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="67218-122">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="67218-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="67218-123">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="67218-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="67218-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="67218-124">E_NOTIMPL</span></span>|<span data-ttu-id="67218-125">Узел не предоставляет реализацию `GetMaxThreads`.</span><span class="sxs-lookup"><span data-stu-id="67218-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67218-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="67218-126">Remarks</span></span>  
 <span data-ttu-id="67218-127">Среда CLR вызывает `GetMaxThreads` определить общее число потоков в пуле потоков.</span><span class="sxs-lookup"><span data-stu-id="67218-127">The CLR calls `GetMaxThreads` to determine the total number of threads in the thread pool.</span></span> <span data-ttu-id="67218-128">[GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) метод возвращает количество потоков, которые в настоящий момент не обрабатывает рабочие элементы.</span><span class="sxs-lookup"><span data-stu-id="67218-128">The [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) method gets the number of threads that are not currently processing work items.</span></span> <span data-ttu-id="67218-129">Все запросы, превышающие возвращаемым значением `pdwMaxWorkerThreads` параметр остаются в очереди до появления доступных потоков.</span><span class="sxs-lookup"><span data-stu-id="67218-129">All requests above the returned value of the `pdwMaxWorkerThreads` parameter remain queued until threads become available.</span></span>  
  
 <span data-ttu-id="67218-130">Если узел не предоставляет реализацию `GetMaxThreads`, он должен возвращать значение HRESULT E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="67218-130">If the host does not provide an implementation of `GetMaxThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67218-131">Требования</span><span class="sxs-lookup"><span data-stu-id="67218-131">Requirements</span></span>  
 <span data-ttu-id="67218-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67218-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67218-133">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="67218-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="67218-134">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67218-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67218-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67218-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67218-136">См. также</span><span class="sxs-lookup"><span data-stu-id="67218-136">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="67218-137">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="67218-137">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="67218-138">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="67218-138">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="67218-139">IHostThreadPoolManager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="67218-139">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)