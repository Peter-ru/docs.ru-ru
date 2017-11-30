---
title: "Метод ICorProfilerInfo::GetObjectSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetObjectSize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8d395d498dd34cb0cbc93e898761c87dcd5ec42a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="c4064-102">Метод ICorProfilerInfo::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="c4064-102">ICorProfilerInfo::GetObjectSize Method</span></span>
<span data-ttu-id="c4064-103">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="c4064-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4064-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4064-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4064-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4064-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="c4064-106">[in] Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="c4064-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="c4064-107">[out] Указатель на размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="c4064-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4064-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c4064-108">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4064-109">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="c4064-109">This method is obsolete.</span></span> <span data-ttu-id="c4064-110">Он возвращает COR_E_OVERFLOW для объектов более 4 ГБ на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="c4064-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="c4064-111">Используйте [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="c4064-111">Use the  [ICorProfilerInfo4::GetObjectSize2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="c4064-112">Разные объекты одного типа часто имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="c4064-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="c4064-113">Однако некоторые типы, например массивов или строк, могут иметь другого размера для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="c4064-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="c4064-114">Размер, возвращаемый `GetObjectSize` метода не включает заполнения выравнивание, может появиться после объекта в куче сбора мусора.</span><span class="sxs-lookup"><span data-stu-id="c4064-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="c4064-115">Если вы используете `GetObjectSize` метод перемещаться от объекта к объекту в куче сбора мусора, добавлять заполнение вручную, при необходимости выравнивания.</span><span class="sxs-lookup"><span data-stu-id="c4064-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
-   <span data-ttu-id="c4064-116">На 32-разрядной версии Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 используется 4-байтовое выравнивание, а COR_PRF_GC_LARGE_OBJECT_HEAP 8-байтового выравнивания.</span><span class="sxs-lookup"><span data-stu-id="c4064-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
-   <span data-ttu-id="c4064-117">На 64-разрядной версии Windows выравнивание всегда равно 8 байт.</span><span class="sxs-lookup"><span data-stu-id="c4064-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4064-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c4064-118">Requirements</span></span>  
 <span data-ttu-id="c4064-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4064-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4064-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4064-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4064-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4064-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4064-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4064-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4064-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c4064-123">See Also</span></span>  
 [<span data-ttu-id="c4064-124">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="c4064-124">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)