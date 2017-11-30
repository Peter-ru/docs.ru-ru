---
title: "Интерфейс IEnumIDENTITY_ATTRIBUTE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumIDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords: IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f88e400556421e0908e0a0b115f66ec3221124c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="532f7-102">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="532f7-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="532f7-103">Служит в качестве перечислителя для атрибутов объекта кода в текущей области.</span><span class="sxs-lookup"><span data-stu-id="532f7-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="532f7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="532f7-104">Methods</span></span>  
  
|<span data-ttu-id="532f7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="532f7-105">Method</span></span>|<span data-ttu-id="532f7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="532f7-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="532f7-107">Получает указатель интерфейса на новый `IEnumIDENTITY_ATTRIBUTE` , содержащий те же элементы, как это `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="532f7-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="532f7-108">Записывает данные, содержащиеся в элементах этого `IEnumIDENTITY_ATTRIBUTE` для указанного буфера данных.</span><span class="sxs-lookup"><span data-stu-id="532f7-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="532f7-109">Возвращает заданное число атрибутов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="532f7-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="532f7-110">Перемещает указатель на начало `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="532f7-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="532f7-111">Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="532f7-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="532f7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="532f7-112">Requirements</span></span>  
 <span data-ttu-id="532f7-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="532f7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532f7-114">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="532f7-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="532f7-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532f7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="532f7-116">See Also</span></span>  
 [<span data-ttu-id="532f7-117">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="532f7-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)