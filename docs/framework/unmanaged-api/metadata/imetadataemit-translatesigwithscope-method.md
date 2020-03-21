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
ms.openlocfilehash: 2662af41fbd2cdc3ce8a6df1e036dfc5b22ff6a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175556"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="c69d1-102">IMetaDataEmit::TranslateSigWithScope (Método)</span><span class="sxs-lookup"><span data-stu-id="c69d1-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="c69d1-103">Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.</span><span class="sxs-lookup"><span data-stu-id="c69d1-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c69d1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c69d1-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="c69d1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c69d1-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="c69d1-106">[en] La interfaz para el ensamblado de importación (donde se define la firma).</span><span class="sxs-lookup"><span data-stu-id="c69d1-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c69d1-107">[en] El blob hash para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c69d1-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c69d1-108">[en] El recuento de `pbHashValue`bytes en .</span><span class="sxs-lookup"><span data-stu-id="c69d1-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="c69d1-109">[en] La interfaz para el ámbito de metadatos de importación.</span><span class="sxs-lookup"><span data-stu-id="c69d1-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="c69d1-110">[en] La firma que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="c69d1-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c69d1-111">[en] El tamaño, en `pbSigBlob`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="c69d1-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="c69d1-112">[en] La interfaz para el ensamblado de exportación.</span><span class="sxs-lookup"><span data-stu-id="c69d1-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="c69d1-113">[en] La interfaz para el ámbito de metadatos de exportación.</span><span class="sxs-lookup"><span data-stu-id="c69d1-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="c69d1-114">[fuera] El búfer que contiene el blob de firma traducido.</span><span class="sxs-lookup"><span data-stu-id="c69d1-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="c69d1-115">[en] La capacidad, en `pvTranslatedSig`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="c69d1-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="c69d1-116">[fuera] El número de bytes reales en la firma traducida.</span><span class="sxs-lookup"><span data-stu-id="c69d1-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c69d1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c69d1-117">Requirements</span></span>  
 <span data-ttu-id="c69d1-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c69d1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c69d1-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c69d1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c69d1-120">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c69d1-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c69d1-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c69d1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69d1-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c69d1-122">See also</span></span>

- [<span data-ttu-id="c69d1-123">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c69d1-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c69d1-124">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c69d1-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="c69d1-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c69d1-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c69d1-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c69d1-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c69d1-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c69d1-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
