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
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003989"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="83ba3-102">IMetaDataEmit::TranslateSigWithScope (Método)</span><span class="sxs-lookup"><span data-stu-id="83ba3-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="83ba3-103">Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.</span><span class="sxs-lookup"><span data-stu-id="83ba3-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ba3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83ba3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="83ba3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="83ba3-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="83ba3-106">de Interfaz para el ensamblado de importación (donde se define la firma).</span><span class="sxs-lookup"><span data-stu-id="83ba3-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="83ba3-107">de Objeto binario hash para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="83ba3-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="83ba3-108">de Recuento de bytes de `pbHashValue` .</span><span class="sxs-lookup"><span data-stu-id="83ba3-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="83ba3-109">de La interfaz para importar el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="83ba3-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="83ba3-110">de Firma que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="83ba3-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="83ba3-111">de Tamaño, en bytes, de `pbSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="83ba3-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="83ba3-112">de Interfaz para el ensamblado de exportación.</span><span class="sxs-lookup"><span data-stu-id="83ba3-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="83ba3-113">de La interfaz para el ámbito de exportación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="83ba3-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="83ba3-114">enuncia Búfer que va a contener el BLOB de firma traducido.</span><span class="sxs-lookup"><span data-stu-id="83ba3-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="83ba3-115">de Capacidad, en bytes, de `pvTranslatedSig` .</span><span class="sxs-lookup"><span data-stu-id="83ba3-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="83ba3-116">enuncia Número de bytes reales de la firma traducida.</span><span class="sxs-lookup"><span data-stu-id="83ba3-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83ba3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83ba3-117">Requirements</span></span>  
 <span data-ttu-id="83ba3-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83ba3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83ba3-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83ba3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83ba3-120">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="83ba3-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83ba3-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83ba3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ba3-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83ba3-122">See also</span></span>

- [<span data-ttu-id="83ba3-123">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ba3-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="83ba3-124">IMetaDataAssemblyImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ba3-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="83ba3-125">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ba3-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="83ba3-126">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ba3-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="83ba3-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83ba3-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
