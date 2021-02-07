---
description: 'Más información sobre: IMetaDataEmit:: Merge (método)'
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
ms.openlocfilehash: 6b78dd20555acf1eaf610ed05d8a37ab6cdeee5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745949"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="0cc71-103">IMetaDataEmit::Merge (Método)</span><span class="sxs-lookup"><span data-stu-id="0cc71-103">IMetaDataEmit::Merge Method</span></span>

<span data-ttu-id="0cc71-104">Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="0cc71-104">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cc71-105">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cc71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cc71-106">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="0cc71-107">de Un puntero a un objeto [IMetaDataImport](imetadataimport-interface.md) que identifica el ámbito importado que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="0cc71-107">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="0cc71-108">de Un puntero a un objeto [IMapToken](imaptoken-interface.md) que especifica la reasignación del token.</span><span class="sxs-lookup"><span data-stu-id="0cc71-108">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="0cc71-109">de Un puntero a un objeto [IUnknown](/cpp/atl/iunknown) que especifica los errores.</span><span class="sxs-lookup"><span data-stu-id="0cc71-109">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cc71-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0cc71-110">Remarks</span></span>  

 <span data-ttu-id="0cc71-111">Llame a [IMetaDataEmit:: mergeend (](imetadataemit-mergeend-method.md) para desencadenar la fusión de metadatos en un solo ámbito.</span><span class="sxs-lookup"><span data-stu-id="0cc71-111">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cc71-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cc71-112">Requirements</span></span>  

 <span data-ttu-id="0cc71-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cc71-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cc71-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0cc71-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0cc71-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0cc71-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cc71-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cc71-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc71-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc71-117">See also</span></span>

- [<span data-ttu-id="0cc71-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc71-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0cc71-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc71-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
