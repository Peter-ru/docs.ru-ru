---
title: "Функция SpawnInstance (Справочник по неуправляемым API)"
description: "Функция SpawnInstance создает новый экземпляр класса."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65050772e2f933583506b6612c32c6060f1d20df
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="spawninstance-function"></a><span data-ttu-id="1d9ec-103">Функция SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="1d9ec-103">SpawnInstance function</span></span>
<span data-ttu-id="1d9ec-104">Создает новый экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1d9ec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d9ec-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="1d9ec-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d9ec-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1d9ec-107">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1d9ec-108">[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="1d9ec-109">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-109">[in] Reserved.</span></span> <span data-ttu-id="1d9ec-110">Этот параметр должен быть 0.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="1d9ec-111">[out] Получает указатель на новый экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="1d9ec-112">Если возникает ошибка, новый объект не возвращается, и `ppNewInstance` влево без изменений.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="1d9ec-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1d9ec-113">Return value</span></span>

<span data-ttu-id="1d9ec-114">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="1d9ec-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1d9ec-115">Константа</span><span class="sxs-lookup"><span data-stu-id="1d9ec-115">Constant</span></span>  |<span data-ttu-id="1d9ec-116">Значение</span><span class="sxs-lookup"><span data-stu-id="1d9ec-116">Value</span></span>  |<span data-ttu-id="1d9ec-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1d9ec-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="1d9ec-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="1d9ec-118">0x80041020</span></span> | <span data-ttu-id="1d9ec-119">`ptr`не является допустимым определением класса и не может создать новые экземпляры.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="1d9ec-120">Он неполон или он не был зарегистрирован с помощью управления Windows путем вызова [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="1d9ec-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1d9ec-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1d9ec-121">0x80041006</span></span> | <span data-ttu-id="1d9ec-122">Недостаточно памяти для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1d9ec-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1d9ec-123">0x80041008</span></span> | <span data-ttu-id="1d9ec-124">Свойство `ppNewClass` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1d9ec-125">0</span><span class="sxs-lookup"><span data-stu-id="1d9ec-125">0</span></span> | <span data-ttu-id="1d9ec-126">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1d9ec-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d9ec-127">Remarks</span></span>

<span data-ttu-id="1d9ec-128">Эта функция создает оболочку для вызова [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1d9ec-129">`ptr`Определение класса приобретаются у управления Windows.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="1d9ec-130">(Обратите внимание, что поддерживается порождает экземпляра из экземпляра, но возвращаемый экземпляр пуст). Затем используйте следующее определение класса для создания новых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="1d9ec-131">Вызов [PutInstanceWmi](putinstancewmi.md) функции является обязательным, если планируется указать экземпляр для управления Windows.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="1d9ec-132">Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="1d9ec-133">Нельзя переопределить это поведение.</span><span class="sxs-lookup"><span data-stu-id="1d9ec-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="1d9ec-134">Нет никакой другой метод, с помощью которого создаются подклассы (классы).</span><span class="sxs-lookup"><span data-stu-id="1d9ec-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="1d9ec-135">Требования</span><span class="sxs-lookup"><span data-stu-id="1d9ec-135">Requirements</span></span>  
 <span data-ttu-id="1d9ec-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d9ec-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d9ec-137">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1d9ec-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1d9ec-138">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9ec-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9ec-139">См. также</span><span class="sxs-lookup"><span data-stu-id="1d9ec-139">See also</span></span>  
[<span data-ttu-id="1d9ec-140">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1d9ec-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)