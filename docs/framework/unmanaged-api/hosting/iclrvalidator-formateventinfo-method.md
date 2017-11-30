---
title: "Метод ICLRValidator::FormatEventInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRValidator.FormatEventInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d03864ac8e4e0423e45ac084e01af98e3eab13a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="0235b-102">Метод ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="0235b-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="0235b-103">Возвращает подробное сообщение об указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="0235b-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0235b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0235b-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0235b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0235b-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="0235b-106">[in] Значение HRESULT, который был передан в обработчик ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="0235b-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="0235b-107">[in] Объект `VEContext` экземпляр, содержащий контекстные сведения об ошибках проверки.</span><span class="sxs-lookup"><span data-stu-id="0235b-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="0235b-108">[in, out] Понятное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0235b-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="0235b-109">[in] Максимальная длина сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="0235b-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="0235b-110">[in] Безопасный массив дополнительных параметров для использования в сообщении.</span><span class="sxs-lookup"><span data-stu-id="0235b-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0235b-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0235b-111">Return Value</span></span>  
  
|<span data-ttu-id="0235b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0235b-112">HRESULT</span></span>|<span data-ttu-id="0235b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0235b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0235b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0235b-114">S_OK</span></span>|<span data-ttu-id="0235b-115">`FormatEventInfo`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="0235b-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="0235b-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0235b-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0235b-117">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0235b-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0235b-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0235b-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0235b-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0235b-119">The call timed out.</span></span>|  
|<span data-ttu-id="0235b-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0235b-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0235b-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0235b-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0235b-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0235b-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0235b-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0235b-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0235b-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0235b-124">E_FAIL</span></span>|<span data-ttu-id="0235b-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0235b-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0235b-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0235b-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0235b-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0235b-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0235b-128">Требования</span><span class="sxs-lookup"><span data-stu-id="0235b-128">Requirements</span></span>  
 <span data-ttu-id="0235b-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0235b-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0235b-130">**Заголовок:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="0235b-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="0235b-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0235b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0235b-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0235b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0235b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0235b-133">See Also</span></span>  
 [<span data-ttu-id="0235b-134">Iclrerrorreportingmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0235b-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="0235b-135">ICLRValidator-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0235b-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)