---
title: "Метод ICorDebugGCReferenceEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGCReferenceEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55a02b88076d6097415d108d58f74565d1f426de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="4bcbc-102">Метод ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="4bcbc-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="4bcbc-103">Возвращает заданное число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) экземпляров, которые содержат сведения об объектах, которые будет собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="4bcbc-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bcbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bcbc-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bcbc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4bcbc-105">Parameters</span></span>  
 <span data-ttu-id="4bcbc-106">celt</span><span class="sxs-lookup"><span data-stu-id="4bcbc-106">celt</span></span>  
 <span data-ttu-id="4bcbc-107">[in] Число корней, которые требуется получить.</span><span class="sxs-lookup"><span data-stu-id="4bcbc-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="4bcbc-108">корни</span><span class="sxs-lookup"><span data-stu-id="4bcbc-108">roots</span></span>  
 <span data-ttu-id="4bcbc-109">[out] Массив указателей, каждый из которых указывает на [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объект, представляющий корень объекта может быть собрана сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="4bcbc-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="4bcbc-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="4bcbc-110">pceltFetched</span></span>  
 <span data-ttu-id="4bcbc-111">[out] Указатель на число [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) объектов, фактически извлеченных в `roots`.</span><span class="sxs-lookup"><span data-stu-id="4bcbc-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="4bcbc-112">Это значение может быть `null`, если параметр `celt` имеет значение 1.</span><span class="sxs-lookup"><span data-stu-id="4bcbc-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bcbc-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bcbc-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bcbc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4bcbc-114">Requirements</span></span>  
 <span data-ttu-id="4bcbc-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bcbc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bcbc-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4bcbc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4bcbc-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bcbc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bcbc-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bcbc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcbc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4bcbc-119">See Also</span></span>  
 [<span data-ttu-id="4bcbc-120">Интерфейс ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="4bcbc-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="4bcbc-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4bcbc-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)