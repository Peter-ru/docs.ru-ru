---
title: "Функция QualifierSet_Put (Справочник по неуправляемым API)"
description: "Функция QualifierSet_Put записывает именованного квалификатора и его значение."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7fdb6759d4e39ad9ab6bd6da2c2a0e2abfbe5d56
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="c16f3-103">Функция QualifierSet_Put</span><span class="sxs-lookup"><span data-stu-id="c16f3-103">QualifierSet_Put function</span></span>
<span data-ttu-id="c16f3-104">Записывает именованный квалификатор и значение.</span><span class="sxs-lookup"><span data-stu-id="c16f3-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="c16f3-105">Новый квалификатор перезаписывает предыдущее значение с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="c16f3-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="c16f3-106">Если квалификатор не существует, он создается.</span><span class="sxs-lookup"><span data-stu-id="c16f3-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c16f3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c16f3-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="c16f3-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c16f3-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="c16f3-109">[in] Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="c16f3-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="c16f3-110">[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c16f3-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="c16f3-111">[in] Имя квалификатора для записи.</span><span class="sxs-lookup"><span data-stu-id="c16f3-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="c16f3-112">`pVal`[in] Указатель на допустимый `VARIANT` , содержащий квалификатор для записи.</span><span class="sxs-lookup"><span data-stu-id="c16f3-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="c16f3-113">Этот параметр не может быть `null`.</span><span class="sxs-lookup"><span data-stu-id="c16f3-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="c16f3-114">`lFlavor`[in] Одно из следующих констант, который определяет требуемый квалификаторов для этого квалификатора.</span><span class="sxs-lookup"><span data-stu-id="c16f3-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="c16f3-115">Значение по умолчанию — `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="c16f3-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="c16f3-116">Константа</span><span class="sxs-lookup"><span data-stu-id="c16f3-116">Constant</span></span>  |<span data-ttu-id="c16f3-117">Значение</span><span class="sxs-lookup"><span data-stu-id="c16f3-117">Value</span></span>  |<span data-ttu-id="c16f3-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c16f3-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="c16f3-119">0</span><span class="sxs-lookup"><span data-stu-id="c16f3-119">0</span></span> | <span data-ttu-id="c16f3-120">Квалификатор можно переопределить в производный класс или экземпляр.</span><span class="sxs-lookup"><span data-stu-id="c16f3-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="c16f3-121">**Это значение по умолчанию.**</span><span class="sxs-lookup"><span data-stu-id="c16f3-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="c16f3-122">1</span><span class="sxs-lookup"><span data-stu-id="c16f3-122">1</span></span> | <span data-ttu-id="c16f3-123">Квалификатор распространяется в экземпляры.</span><span class="sxs-lookup"><span data-stu-id="c16f3-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="c16f3-124">2</span><span class="sxs-lookup"><span data-stu-id="c16f3-124">2</span></span> | <span data-ttu-id="c16f3-125">Квалификатор распространяется на производные классы.</span><span class="sxs-lookup"><span data-stu-id="c16f3-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="c16f3-126">"WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="c16f3-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="c16f3-127">0x10</span><span class="sxs-lookup"><span data-stu-id="c16f3-127">0x10</span></span> | <span data-ttu-id="c16f3-128">Квалификатор невозможно переопределить в производном классе или экземпляре.</span><span class="sxs-lookup"><span data-stu-id="c16f3-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="c16f3-129">"WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="c16f3-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="c16f3-130">0x80</span><span class="sxs-lookup"><span data-stu-id="c16f3-130">0x80</span></span> | <span data-ttu-id="c16f3-131">Квалификатор локализован.</span><span class="sxs-lookup"><span data-stu-id="c16f3-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="c16f3-132">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c16f3-132">Return value</span></span>

<span data-ttu-id="c16f3-133">Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="c16f3-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c16f3-134">Константа</span><span class="sxs-lookup"><span data-stu-id="c16f3-134">Constant</span></span>  |<span data-ttu-id="c16f3-135">Значение</span><span class="sxs-lookup"><span data-stu-id="c16f3-135">Value</span></span>  |<span data-ttu-id="c16f3-136">Описание</span><span class="sxs-lookup"><span data-stu-id="c16f3-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="c16f3-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="c16f3-137">0x8004101f</span></span> | <span data-ttu-id="c16f3-138">Возникла Недопустимая попытка задать **ключ** квалификатор для свойства, которое не может быть ключом.</span><span class="sxs-lookup"><span data-stu-id="c16f3-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="c16f3-139">Указанные ключи om c; ASS Разрешить определение объекта и не может быть изменены для каждого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="c16f3-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c16f3-140">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c16f3-140">0x80041008</span></span> | <span data-ttu-id="c16f3-141">Параметр не является допустимым.</span><span class="sxs-lookup"><span data-stu-id="c16f3-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="c16f3-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="c16f3-142">0x80041029</span></span> | <span data-ttu-id="c16f3-143">`pVal` Параметр не является правильным типом квалификатора.</span><span class="sxs-lookup"><span data-stu-id="c16f3-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="c16f3-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="c16f3-144">0x8004101a</span></span> | <span data-ttu-id="c16f3-145">Невозможно вызвать `QualifierSet_Put` метод квалификатор, поскольку объект-владелец не разрешает переопределения.</span><span class="sxs-lookup"><span data-stu-id="c16f3-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c16f3-146">0</span><span class="sxs-lookup"><span data-stu-id="c16f3-146">0</span></span> | <span data-ttu-id="c16f3-147">Успешный вызов функции.</span><span class="sxs-lookup"><span data-stu-id="c16f3-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="c16f3-148">Примечания</span><span class="sxs-lookup"><span data-stu-id="c16f3-148">Remarks</span></span>

<span data-ttu-id="c16f3-149">Эта функция создает оболочку для вызова [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) метод.</span><span class="sxs-lookup"><span data-stu-id="c16f3-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c16f3-150">Требования</span><span class="sxs-lookup"><span data-stu-id="c16f3-150">Requirements</span></span>  
 <span data-ttu-id="c16f3-151">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c16f3-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c16f3-152">**Заголовок:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c16f3-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c16f3-153">**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c16f3-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16f3-154">См. также</span><span class="sxs-lookup"><span data-stu-id="c16f3-154">See also</span></span>  
[<span data-ttu-id="c16f3-155">WMI и счетчиков производительности (Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="c16f3-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)