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
ms.openlocfilehash: 759358822ed865c89f6f55084d1e7f6143506e93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175712"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="4c4b5-102">IMetaDataEmit::Merge (Método)</span><span class="sxs-lookup"><span data-stu-id="4c4b5-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="4c4b5-103">Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="4c4b5-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c4b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c4b5-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c4b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4c4b5-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="4c4b5-106">[en] Puntero a un objeto [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) que identifica el ámbito importado que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="4c4b5-106">[in] A pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="4c4b5-107">[en] Puntero a un objeto [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) que especifica el mapa de token.</span><span class="sxs-lookup"><span data-stu-id="4c4b5-107">[in] A pointer to an [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="4c4b5-108">[en] Puntero a un objeto [IUnknown](/cpp/atl/iunknown) que especifica los errores.</span><span class="sxs-lookup"><span data-stu-id="4c4b5-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c4b5-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c4b5-109">Remarks</span></span>  
 <span data-ttu-id="4c4b5-110">Llame a [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) para desencadenar la combinación de metadatos en un único ámbito.</span><span class="sxs-lookup"><span data-stu-id="4c4b5-110">Call [IMetaDataEmit::MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c4b5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c4b5-111">Requirements</span></span>  
 <span data-ttu-id="4c4b5-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c4b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c4b5-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4c4b5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c4b5-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c4b5-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c4b5-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c4b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c4b5-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c4b5-116">See also</span></span>

- [<span data-ttu-id="4c4b5-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c4b5-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4c4b5-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c4b5-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
