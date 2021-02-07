---
description: 'Más información sobre: IMetaDataEmit:: TranslateSigWithScope ((método)'
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
ms.openlocfilehash: e5f4e522e993f2f391ca0c29e5fcc2cbb71775e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720939"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="593a5-103">IMetaDataEmit::TranslateSigWithScope (Método)</span><span class="sxs-lookup"><span data-stu-id="593a5-103">IMetaDataEmit::TranslateSigWithScope Method</span></span>

<span data-ttu-id="593a5-104">Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.</span><span class="sxs-lookup"><span data-stu-id="593a5-104">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593a5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="593a5-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="593a5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="593a5-106">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="593a5-107">de Interfaz para el ensamblado de importación (donde se define la firma).</span><span class="sxs-lookup"><span data-stu-id="593a5-107">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="593a5-108">de Objeto binario hash para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="593a5-108">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="593a5-109">de Recuento de bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="593a5-109">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="593a5-110">de La interfaz para importar el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="593a5-110">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="593a5-111">de Firma que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="593a5-111">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="593a5-112">de Tamaño, en bytes, de `pbSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="593a5-112">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="593a5-113">de Interfaz para el ensamblado de exportación.</span><span class="sxs-lookup"><span data-stu-id="593a5-113">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="593a5-114">de La interfaz para el ámbito de exportación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="593a5-114">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="593a5-115">enuncia Búfer que va a contener el BLOB de firma traducido.</span><span class="sxs-lookup"><span data-stu-id="593a5-115">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="593a5-116">de Capacidad, en bytes, de `pvTranslatedSig` .</span><span class="sxs-lookup"><span data-stu-id="593a5-116">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="593a5-117">enuncia Número de bytes reales de la firma traducida.</span><span class="sxs-lookup"><span data-stu-id="593a5-117">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="593a5-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="593a5-118">Requirements</span></span>  

 <span data-ttu-id="593a5-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="593a5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="593a5-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="593a5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="593a5-121">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="593a5-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="593a5-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="593a5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593a5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="593a5-123">See also</span></span>

- [<span data-ttu-id="593a5-124">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="593a5-124">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="593a5-125">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="593a5-125">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="593a5-126">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="593a5-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="593a5-127">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="593a5-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="593a5-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="593a5-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
