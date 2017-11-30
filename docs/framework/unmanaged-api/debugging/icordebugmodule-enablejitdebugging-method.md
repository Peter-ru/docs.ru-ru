---
title: "Метод ICorDebugModule::EnableJITDebugging"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableJITDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31fc3b7c2b977dbfd6f10cc767f81748243dfce4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="23332-102">Метод ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="23332-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="23332-103">Определяет, сохраняет ли компилятор just-in-time (JIT), сведения об отладке для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="23332-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23332-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="23332-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23332-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="23332-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="23332-106">[in] Это значение равно `true` для включения JIT-компилятором для сохранения сведений о сопоставлении между версией Microsoft промежуточного языка MSIL и версии JIT-компиляции каждого метода в данном модуле.</span><span class="sxs-lookup"><span data-stu-id="23332-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="23332-107">[in] Это значение равно `true` для включения JIT-компилятору создавать код с помощью определенные оптимизации конкретных JIT-компилятора для отладки.</span><span class="sxs-lookup"><span data-stu-id="23332-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23332-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="23332-108">Remarks</span></span>  
 <span data-ttu-id="23332-109">JIT-отладка включена по умолчанию для всех модулей, загруженных при активном отладчик.</span><span class="sxs-lookup"><span data-stu-id="23332-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="23332-110">Программное Включение или отключение параметров переопределяет глобальные настройки.</span><span class="sxs-lookup"><span data-stu-id="23332-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23332-111">Требования</span><span class="sxs-lookup"><span data-stu-id="23332-111">Requirements</span></span>  
 <span data-ttu-id="23332-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23332-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23332-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23332-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23332-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23332-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23332-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23332-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>