---
title: "Метод IMetaDataAssemblyImport::GetAssemblyProps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3ff9c66d483392823a1cc95163e4d5e7e81a364
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="3b8cc-102">Метод IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="3b8cc-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="3b8cc-103">Получает набор свойств для сборки с заданной подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b8cc-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b8cc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b8cc-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="3b8cc-106">[in].</span><span class="sxs-lookup"><span data-stu-id="3b8cc-106">[in].</span></span> <span data-ttu-id="3b8cc-107">`mdAssembly` Токен метаданных, представляющий сборку, для которого нужно получить свойства.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="3b8cc-108">[out] Указатель на открытый ключ или маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="3b8cc-109">[out] Число байтов в возвращаемый открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="3b8cc-110">[out] Указатель на алгоритм, используемый для хэширования файлов в сборке.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="3b8cc-111">[out] Простое имя сборки.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3b8cc-112">[in] Размер в расширенных символов из `szName`.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="3b8cc-113">[out] Число расширенных символов, фактически извлеченных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="3b8cc-114">[out] Указатель на структуру ASSEMBLYMETADATA, которая содержит метаданные сборки.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="3b8cc-115">[out] Флаги, описывающие метаданные, применяемые к сборке.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="3b8cc-116">Это значение представляет собой сочетание одного или нескольких [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) значения.</span><span class="sxs-lookup"><span data-stu-id="3b8cc-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b8cc-117">Требования</span><span class="sxs-lookup"><span data-stu-id="3b8cc-117">Requirements</span></span>  
 <span data-ttu-id="3b8cc-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b8cc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b8cc-119">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b8cc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b8cc-120">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b8cc-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b8cc-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b8cc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b8cc-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3b8cc-122">See Also</span></span>  
 [<span data-ttu-id="3b8cc-123">Imetadataassemblyimport-интерфейс</span><span class="sxs-lookup"><span data-stu-id="3b8cc-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)