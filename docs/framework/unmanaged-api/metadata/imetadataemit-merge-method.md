---
title: IMetaDataEmit::Merge (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Merge
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Merge
helpviewer_keywords:
- IMetaDataEmit::Merge method [.NET Framework metadata]
- Merge method [.NET Framework metadata]
ms.assetid: 7596220c-f699-4b6c-8ae7-c83220610650
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 899f2ca5ef1b987687f5c065ad3e1965e142d103
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216111"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="ca5cc-102">IMetaDataEmit::Merge (Método)</span><span class="sxs-lookup"><span data-stu-id="ca5cc-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="ca5cc-103">Agrega el ámbito importado especificado a la lista de ámbitos que se combinarán.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca5cc-104">Syntax</span></span>  
  
```  
HRESULT Merge (   
    [in]  IMetaDataImport  *pImport,   
    [in]  IMapToken        *pHostMapToken,   
    [in]  IUnknown         *pHandler   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca5cc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca5cc-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="ca5cc-106">[in] Un puntero a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) objeto que identifica el ámbito importado que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="ca5cc-107">[in] Un puntero a un [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) objeto que especifica el token volver a asignar.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandleer`  
 <span data-ttu-id="ca5cc-108">[in] Un puntero a un [IUnknown](/cpp/atl/iunknown) objeto que especifica los errores.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca5cc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca5cc-109">Remarks</span></span>  
 <span data-ttu-id="ca5cc-110">Llame a [MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) para desencadenar la combinación de metadatos en un solo ámbito.</span><span class="sxs-lookup"><span data-stu-id="ca5cc-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5cc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca5cc-111">Requirements</span></span>  
 <span data-ttu-id="ca5cc-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca5cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5cc-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca5cc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca5cc-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ca5cc-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca5cc-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5cc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca5cc-116">See Also</span></span>  
 [<span data-ttu-id="ca5cc-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca5cc-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ca5cc-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca5cc-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
