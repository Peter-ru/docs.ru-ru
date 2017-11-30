---
title: "Перечисление CorDebugCodeInvokeKind"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCodeInvokeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: e795e6a2-1008-4a81-af88-d777888e942e
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d46a47c7c655a960224bb836be0ea37cd07c8038
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugcodeinvokekind-enumeration"></a><span data-ttu-id="0c725-102">Перечисление CorDebugCodeInvokeKind</span><span class="sxs-lookup"><span data-stu-id="0c725-102">CorDebugCodeInvokeKind Enumeration</span></span>
<span data-ttu-id="0c725-103">Описывает, каким образом экспортируемая функция вызывает управляемый код.</span><span class="sxs-lookup"><span data-stu-id="0c725-103">Describes how an exported function invokes managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c725-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c725-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokeKind  
{  
    CODE_INVOKE_KIND_NONE,       
    CODE_INVOKE_KIND_RETURN,     
    CODE_INVOKE_KIND_TAILCALL,   
} CorDebugCodeInvokeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="0c725-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0c725-105">Members</span></span>  
  
|<span data-ttu-id="0c725-106">Член</span><span class="sxs-lookup"><span data-stu-id="0c725-106">Member</span></span>|<span data-ttu-id="0c725-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0c725-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_KIND_NONE`|<span data-ttu-id="0c725-108">Если любой управляемый код вызывается этим методом, он должен находиться после явно заданных событий или точек останова.</span><span class="sxs-lookup"><span data-stu-id="0c725-108">If any managed code is invoked by this method, it will have to be located by explicit events or breakpoints later.</span></span><br /><br /> <span data-ttu-id="0c725-109">— или —</span><span class="sxs-lookup"><span data-stu-id="0c725-109">--or--</span></span><br /><br /> <span data-ttu-id="0c725-110">Мы можем просто пропустить некоторую часть управляемого кода, который вызывает этот метод, так как не существует никакого простого способа останова на нем.</span><span class="sxs-lookup"><span data-stu-id="0c725-110">We may just miss some of the managed code this method calls because there is no easy way to stop on it.</span></span><br /><br /> <span data-ttu-id="0c725-111">— или —</span><span class="sxs-lookup"><span data-stu-id="0c725-111">--or--</span></span><br /><br /> <span data-ttu-id="0c725-112">Метод может никогда не вызвать управляемый код.</span><span class="sxs-lookup"><span data-stu-id="0c725-112">The method may never invoke managed code.</span></span>|  
|`CODE_INVOKE_KIND_RETURN`|<span data-ttu-id="0c725-113">Этот метод будет вызывать управляемый код с помощью инструкции return.</span><span class="sxs-lookup"><span data-stu-id="0c725-113">This method will invoke managed code via a return instruction.</span></span> <span data-ttu-id="0c725-114">Режим пропуска должен начаться в следующем управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="0c725-114">Stepping out should arrive at the next managed code.</span></span>|  
|`CODE_INVOKE_KIND_TAILCALL`|<span data-ttu-id="0c725-115">Этот метод будет вызывать управляемый код с помощью вызова с префиксом tail.</span><span class="sxs-lookup"><span data-stu-id="0c725-115">This method will invoke managed code via a tail-call.</span></span> <span data-ttu-id="0c725-116">Пошаговый режим и режим пропуска любых инструкций вызова должны поступать в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="0c725-116">Single-stepping and stepping over any call instructions should arrive at managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c725-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c725-117">Remarks</span></span>  
 <span data-ttu-id="0c725-118">Это перечисление используется методом [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) информацию о пошаговом выполнении управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0c725-118">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c725-119">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0c725-119">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c725-120">Требования</span><span class="sxs-lookup"><span data-stu-id="0c725-120">Requirements</span></span>  
 <span data-ttu-id="0c725-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c725-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c725-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c725-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c725-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c725-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c725-124">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c725-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c725-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0c725-125">See Also</span></span>  
 [<span data-ttu-id="0c725-126">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0c725-126">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="0c725-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="0c725-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)