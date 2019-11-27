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
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440475"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="aa853-102">IMetaDataEmit::TranslateSigWithScope (Método)</span><span class="sxs-lookup"><span data-stu-id="aa853-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="aa853-103">Importa un ensamblado en el ámbito actual y obtiene una nueva firma de metadatos para el ámbito combinado.</span><span class="sxs-lookup"><span data-stu-id="aa853-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa853-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa853-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="aa853-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa853-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="aa853-106">de Interfaz para el ensamblado de importación (donde se define la firma).</span><span class="sxs-lookup"><span data-stu-id="aa853-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="aa853-107">de Objeto binario hash para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aa853-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="aa853-108">de Recuento de bytes de `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="aa853-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="aa853-109">de La interfaz para importar el ámbito de metadatos.</span><span class="sxs-lookup"><span data-stu-id="aa853-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="aa853-110">de Firma que se va a importar.</span><span class="sxs-lookup"><span data-stu-id="aa853-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="aa853-111">de Tamaño, en bytes, de `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="aa853-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="aa853-112">de Interfaz para el ensamblado de exportación.</span><span class="sxs-lookup"><span data-stu-id="aa853-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="aa853-113">de La interfaz para el ámbito de exportación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="aa853-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="aa853-114">enuncia Búfer que va a contener el BLOB de firma traducido.</span><span class="sxs-lookup"><span data-stu-id="aa853-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="aa853-115">de La capacidad, en bytes, de `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="aa853-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="aa853-116">enuncia Número de bytes reales de la firma traducida.</span><span class="sxs-lookup"><span data-stu-id="aa853-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa853-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa853-117">Requirements</span></span>  
 <span data-ttu-id="aa853-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa853-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa853-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aa853-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa853-120">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aa853-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa853-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa853-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa853-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa853-122">See also</span></span>

- [<span data-ttu-id="aa853-123">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa853-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="aa853-124">IMetaDataAssemblyImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa853-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="aa853-125">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa853-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa853-126">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa853-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="aa853-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa853-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
