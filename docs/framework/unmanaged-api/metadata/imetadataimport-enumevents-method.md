---
title: IMetaDataImport::EnumEvents (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f205615db29878bcfe936e88cab26c3d5a8e3562
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514535"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="69e5f-102">IMetaDataImport::EnumEvents (Método)</span><span class="sxs-lookup"><span data-stu-id="69e5f-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="69e5f-103">Enumera los tokens de definición de eventos del token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="69e5f-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69e5f-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69e5f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69e5f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="69e5f-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="69e5f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="69e5f-107">[in] El token de TypeDef cuyas definiciones de evento son que hay que enumerar.</span><span class="sxs-lookup"><span data-stu-id="69e5f-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="69e5f-108">[out] Matriz de eventos devueltos.</span><span class="sxs-lookup"><span data-stu-id="69e5f-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="69e5f-109">[in] Tamaño máximo de la matriz `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="69e5f-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="69e5f-110">[out] El número real de los eventos devueltos en `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="69e5f-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69e5f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69e5f-111">Return Value</span></span>  
  
|<span data-ttu-id="69e5f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69e5f-112">HRESULT</span></span>|<span data-ttu-id="69e5f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="69e5f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="69e5f-114">`EnumEvents` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="69e5f-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="69e5f-115">No hay ningún evento para enumerar.</span><span class="sxs-lookup"><span data-stu-id="69e5f-115">There are no events to enumerate.</span></span> <span data-ttu-id="69e5f-116">En ese caso, `pcEvents` es cero.</span><span class="sxs-lookup"><span data-stu-id="69e5f-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69e5f-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69e5f-117">Requirements</span></span>  
 <span data-ttu-id="69e5f-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69e5f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e5f-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="69e5f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69e5f-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69e5f-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69e5f-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e5f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e5f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="69e5f-122">See also</span></span>
- [<span data-ttu-id="69e5f-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69e5f-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="69e5f-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69e5f-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
