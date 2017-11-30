---
title: "Интерфейс IHostIoCompletionManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager
helpviewer_keywords: IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 847d4c3aa3e3da94b4aac4679ada047577379f82
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ihostiocompletionmanager-interface"></a><span data-ttu-id="b314b-102">Интерфейс IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="b314b-102">IHostIoCompletionManager Interface</span></span>
<span data-ttu-id="b314b-103">Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с порты завершения ввода-вывода, предоставленный средой размещения.</span><span class="sxs-lookup"><span data-stu-id="b314b-103">Provides methods that allow the common language runtime (CLR) to interact with I/O completion ports provided by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b314b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b314b-104">Methods</span></span>  
  
|<span data-ttu-id="b314b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b314b-105">Method</span></span>|<span data-ttu-id="b314b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b314b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b314b-107">Метод Bind</span><span class="sxs-lookup"><span data-stu-id="b314b-107">Bind Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|<span data-ttu-id="b314b-108">Привязывает дескриптор к порту завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-108">Binds a handle to an I/O completion port.</span></span>|  
|[<span data-ttu-id="b314b-109">Closeiocompletionport-метод</span><span class="sxs-lookup"><span data-stu-id="b314b-109">CloseIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|<span data-ttu-id="b314b-110">Закрывает порт, который был создан при помощи предыдущими вызовами метода `CreateIoCompletionPort`.</span><span class="sxs-lookup"><span data-stu-id="b314b-110">Closes a port that was created through an earlier call to `CreateIoCompletionPort`.</span></span>|  
|[<span data-ttu-id="b314b-111">CreateIoCompletionPort-метод</span><span class="sxs-lookup"><span data-stu-id="b314b-111">CreateIoCompletionPort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|<span data-ttu-id="b314b-112">Запросы на создание нового порта завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-112">Requests that the host create a new I/O completion port.</span></span>|  
|[<span data-ttu-id="b314b-113">Метод GetAvailableThreads</span><span class="sxs-lookup"><span data-stu-id="b314b-113">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|<span data-ttu-id="b314b-114">Возвращает число потоков завершения ввода-вывода, которые в настоящий момент не обрабатывает запросы.</span><span class="sxs-lookup"><span data-stu-id="b314b-114">Gets the number of I/O completion threads that are not currently processing requests.</span></span>|  
|[<span data-ttu-id="b314b-115">Gethostoverlappedsize-метод</span><span class="sxs-lookup"><span data-stu-id="b314b-115">GetHostOverlappedSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|<span data-ttu-id="b314b-116">Получает размер любых пользовательских данных, которые должен узла для добавления запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-116">Gets the size of any custom data the host intends to append to I/O requests.</span></span>|  
|[<span data-ttu-id="b314b-117">Метод GetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b314b-117">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|<span data-ttu-id="b314b-118">Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-118">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>|  
|[<span data-ttu-id="b314b-119">Метод GetMinThreads</span><span class="sxs-lookup"><span data-stu-id="b314b-119">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|<span data-ttu-id="b314b-120">Получает минимальное количество потоков, предоставляемых основным приложением для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-120">Gets the minimum number of threads that the host provides to service I/O requests.</span></span>|  
|[<span data-ttu-id="b314b-121">Initializehostoverlapped-метод</span><span class="sxs-lookup"><span data-stu-id="b314b-121">InitializeHostOverlapped Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|<span data-ttu-id="b314b-122">Предоставляет основному приложению возможность инициализировать любые пользовательские данные о запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-122">Provides the host with an opportunity to initialize any custom data about an I/O request.</span></span>|  
|[<span data-ttu-id="b314b-123">Setclriocompletionmanager-метод</span><span class="sxs-lookup"><span data-stu-id="b314b-123">SetCLRIoCompletionManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|<span data-ttu-id="b314b-124">Предоставляет основному указатель интерфейса [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемых средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b314b-124">Provides the host with an interface pointer to an [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the CLR.</span></span>|  
|[<span data-ttu-id="b314b-125">Метод SetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b314b-125">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|<span data-ttu-id="b314b-126">Задает максимальное число потоков, выделяемых основным приложением для обслуживания запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-126">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>|  
|[<span data-ttu-id="b314b-127">Метод SetMinThreads</span><span class="sxs-lookup"><span data-stu-id="b314b-127">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|<span data-ttu-id="b314b-128">Задает минимальное количество потоков, которые основное приложение должно выделить для завершения ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-128">Sets the minimum number of threads that the host should allot to I/O completion.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b314b-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="b314b-129">Remarks</span></span>  
 <span data-ttu-id="b314b-130">`IHostIoCompletionManager`соответствует `ICLRIoCompletionManager` интерфейс, реализованный средой CLR.</span><span class="sxs-lookup"><span data-stu-id="b314b-130">`IHostIoCompletionManager` corresponds to the `ICLRIoCompletionManager` interface implemented by the CLR.</span></span> <span data-ttu-id="b314b-131">Среда CLR вызывает методы `IHostIoCompletionManager` для привязки портов, которые предоставляет узел и узел вызывает методы дескрипторы `ICLRIoCompletionManager` для сообщения о завершении запросов ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="b314b-131">The CLR calls the methods of `IHostIoCompletionManager` to bind handles to the ports that the host provides, and the host calls the methods of `ICLRIoCompletionManager` to report the completion of I/O requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b314b-132">Требования</span><span class="sxs-lookup"><span data-stu-id="b314b-132">Requirements</span></span>  
 <span data-ttu-id="b314b-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b314b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b314b-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b314b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b314b-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b314b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b314b-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b314b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b314b-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b314b-137">See Also</span></span>  
 [<span data-ttu-id="b314b-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="b314b-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)