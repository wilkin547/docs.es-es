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
ms.openlocfilehash: e64d644b511f7c3249c48b9642bfd3163142af3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722016"
---
# <a name="imetadataemitmerge-method"></a><span data-ttu-id="7e8c9-102">IMetaDataEmit::Merge (Método)</span><span class="sxs-lookup"><span data-stu-id="7e8c9-102">IMetaDataEmit::Merge Method</span></span>

<span data-ttu-id="7e8c9-103">Agrega el ámbito importado especificado a la lista de ámbitos que se van a combinar.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-103">Adds the specified imported scope to the list of scopes to be merged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e8c9-104">Syntax</span></span>  
  
```cpp  
HRESULT Merge (
    [in]  IMetaDataImport  *pImport,
    [in]  IMapToken        *pHostMapToken,
    [in]  IUnknown         *pHandler
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e8c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e8c9-105">Parameters</span></span>  

 `pImport`  
 <span data-ttu-id="7e8c9-106">de Un puntero a un objeto [IMetaDataImport](imetadataimport-interface.md) que identifica el ámbito importado que se va a combinar.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-106">[in] A pointer to an [IMetaDataImport](imetadataimport-interface.md) object that identifies the imported scope to be merged.</span></span>  
  
 `pIMap`  
 <span data-ttu-id="7e8c9-107">de Un puntero a un objeto [IMapToken](imaptoken-interface.md) que especifica la reasignación del token.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-107">[in] A pointer to an [IMapToken](imaptoken-interface.md) object that specifies the token re-map.</span></span>  
  
 `pHandler`  
 <span data-ttu-id="7e8c9-108">de Un puntero a un objeto [IUnknown](/cpp/atl/iunknown) que especifica los errores.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-108">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) object that specifies the errors.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e8c9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7e8c9-109">Remarks</span></span>  

 <span data-ttu-id="7e8c9-110">Llame a [IMetaDataEmit:: mergeend (](imetadataemit-mergeend-method.md) para desencadenar la fusión de metadatos en un solo ámbito.</span><span class="sxs-lookup"><span data-stu-id="7e8c9-110">Call [IMetaDataEmit::MergeEnd](imetadataemit-mergeend-method.md) to trigger the merger of metadata into a single scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8c9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e8c9-111">Requirements</span></span>  

 <span data-ttu-id="7e8c9-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e8c9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e8c9-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e8c9-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e8c9-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e8c9-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e8c9-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e8c9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8c9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7e8c9-116">See also</span></span>

- [<span data-ttu-id="7e8c9-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e8c9-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="7e8c9-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e8c9-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
