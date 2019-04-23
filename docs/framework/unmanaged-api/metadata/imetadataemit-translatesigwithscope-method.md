---
title: IMetaDataEmit::TranslateSigWithScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71029d6ebfb3248da791d4371dfe3e39589af443
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207648"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="acc3b-102">IMetaDataEmit::TranslateSigWithScope (Método)</span><span class="sxs-lookup"><span data-stu-id="acc3b-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="acc3b-103">Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.</span><span class="sxs-lookup"><span data-stu-id="acc3b-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acc3b-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="acc3b-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="acc3b-106">[in] La interfaz de ensamblado de importación (donde se define la firma).</span><span class="sxs-lookup"><span data-stu-id="acc3b-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="acc3b-107">[in] El blob de hash para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="acc3b-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="acc3b-108">[in] El recuento de bytes en `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="acc3b-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="acc3b-109">[in] La interfaz para el ámbito de metadatos de importación.</span><span class="sxs-lookup"><span data-stu-id="acc3b-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="acc3b-110">[in] La firma que desea importar.</span><span class="sxs-lookup"><span data-stu-id="acc3b-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="acc3b-111">[in] El tamaño, en bytes, de `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="acc3b-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="acc3b-112">[in] La interfaz de ensamblado de exportación.</span><span class="sxs-lookup"><span data-stu-id="acc3b-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="acc3b-113">[in] La interfaz para el ámbito de metadatos de exportación.</span><span class="sxs-lookup"><span data-stu-id="acc3b-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="acc3b-114">[out] El búfer para almacenar el objeto binario de firma traducidos.</span><span class="sxs-lookup"><span data-stu-id="acc3b-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="acc3b-115">[in] La capacidad, en bytes, de `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="acc3b-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="acc3b-116">[out] El número de bytes reales en la firma convertida.</span><span class="sxs-lookup"><span data-stu-id="acc3b-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc3b-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acc3b-117">Requirements</span></span>  
 <span data-ttu-id="acc3b-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acc3b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc3b-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="acc3b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acc3b-120">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acc3b-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acc3b-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc3b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc3b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="acc3b-122">See also</span></span>

- [<span data-ttu-id="acc3b-123">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acc3b-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="acc3b-124">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acc3b-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="acc3b-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acc3b-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="acc3b-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acc3b-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="acc3b-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acc3b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
