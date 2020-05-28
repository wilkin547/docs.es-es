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
ms.openlocfilehash: e7fe5cbe27c0771a71e4c03d14ab68ada7d0741a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004197"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="dc275-102">IMetaDataEmit::Merge (Método)</span><span class="sxs-lookup"><span data-stu-id="dc275-102">IMetaDataEmit::Merge Method</span></span>
<span data-ttu-id="dc275-103">Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="dc275-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc275-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc275-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc275-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc275-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="dc275-106">de Un puntero a un objeto [IMetaDataImport](imetadataimport-interface.md) que identifica el ámbito importado que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="dc275-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="dc275-107">de Un puntero a un objeto [IMapToken](imaptoken-interface.md) que especifica la reasignación del token.</span><span class="sxs-lookup"><span data-stu-id="dc275-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="dc275-108">de Un puntero a un objeto [IUnknown](/cpp/atl/iunknown) que especifica los errores.</span><span class="sxs-lookup"><span data-stu-id="dc275-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc275-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc275-109">Remarks</span></span>  
 <span data-ttu-id="dc275-110">Llame a [IMetaDataEmit:: mergeend (](imetadataemit-mergeend-method.md) para desencadenar la fusión de metadatos en un solo ámbito.</span><span class="sxs-lookup"><span data-stu-id="dc275-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc275-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc275-111">Requirements</span></span>  
 <span data-ttu-id="dc275-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc275-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc275-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc275-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc275-114">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dc275-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc275-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc275-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc275-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc275-116">See also</span></span>

- [<span data-ttu-id="dc275-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc275-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="dc275-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc275-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
