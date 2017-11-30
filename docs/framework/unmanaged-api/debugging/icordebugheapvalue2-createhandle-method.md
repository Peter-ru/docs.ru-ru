---
title: "Метод ICorDebugHeapValue2::CreateHandle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2.CreateHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7feef9af174a63976729f91b5a0b4967fea55b23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="d2e86-102">Метод ICorDebugHeapValue2::CreateHandle</span><span class="sxs-lookup"><span data-stu-id="d2e86-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="d2e86-103">Создает дескриптор указанного типа для значения кучи, представленный этим объектом ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="d2e86-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e86-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e86-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d2e86-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2e86-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="d2e86-106">[in] Значение cordebughandletype-перечисление, указывающее тип дескриптора.</span><span class="sxs-lookup"><span data-stu-id="d2e86-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="d2e86-107">[out] Указатель на адрес объекта ICorDebugHandleValue, который представляет новый маркер для этого значения кучи.</span><span class="sxs-lookup"><span data-stu-id="d2e86-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e86-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2e86-108">Remarks</span></span>  
 <span data-ttu-id="d2e86-109">Дескриптор создается в домене приложения, связанный со значением кучи и станут недопустимыми, если момента выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d2e86-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="d2e86-110">Несколько вызовов этой функции для одного значения кучи создадут множественные дескрипторы.</span><span class="sxs-lookup"><span data-stu-id="d2e86-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="d2e86-111">Так как дескрипторы влияют на производительность сборщика мусора, отладчик должен задать ограничение относительно небольшого числа дескрипторов (около 256), которые активны одновременно.</span><span class="sxs-lookup"><span data-stu-id="d2e86-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e86-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d2e86-112">Requirements</span></span>  
 <span data-ttu-id="d2e86-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e86-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e86-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2e86-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2e86-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2e86-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2e86-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e86-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>