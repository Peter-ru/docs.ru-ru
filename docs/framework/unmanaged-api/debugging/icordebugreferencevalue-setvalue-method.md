---
title: "Метод ICorDebugReferenceValue::SetValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.SetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::SetValue
helpviewer_keywords:
- SetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::SetValue method [.NET Framework debugging]
ms.assetid: 3d3f6eec-d772-401f-a028-1a2ecdc31e95
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 764b99b5687c171b0dcdbc7f8ca15493c182ff7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluesetvalue-method"></a><span data-ttu-id="30cff-102">Метод ICorDebugReferenceValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="30cff-102">ICorDebugReferenceValue::SetValue Method</span></span>
<span data-ttu-id="30cff-103">Задает указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="30cff-103">Sets the specified memory address.</span></span> <span data-ttu-id="30cff-104">То есть этот метод задает этот ICorDebugReferenceValue, чтобы он указывал на объект.</span><span class="sxs-lookup"><span data-stu-id="30cff-104">That is, this method sets this ICorDebugReferenceValue to point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30cff-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30cff-105">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] CORDB_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30cff-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="30cff-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="30cff-107">[in] Объект `CORDB_ADDRESS` значение, указывающее адрес объекта, к которому `ICorDebugReferenceValue` точек.</span><span class="sxs-lookup"><span data-stu-id="30cff-107">[in] A `CORDB_ADDRESS` value that specifies the address of the object to which this `ICorDebugReferenceValue` points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30cff-108">Требования</span><span class="sxs-lookup"><span data-stu-id="30cff-108">Requirements</span></span>  
 <span data-ttu-id="30cff-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30cff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30cff-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30cff-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30cff-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30cff-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30cff-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30cff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>