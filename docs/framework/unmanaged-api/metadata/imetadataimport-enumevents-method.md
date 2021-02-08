---
description: 'Más información sobre: IMetaDataImport:: Enumevents ((método)'
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
ms.openlocfilehash: e944c15a19314b315e01493836ce078fccc917eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799413"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="50b71-103">IMetaDataImport::EnumEvents (Método)</span><span class="sxs-lookup"><span data-stu-id="50b71-103">IMetaDataImport::EnumEvents Method</span></span>

<span data-ttu-id="50b71-104">Enumera los tokens de definición de eventos del token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="50b71-104">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50b71-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50b71-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="50b71-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="50b71-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="50b71-108">de El token de TypeDef cuyas definiciones de evento se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="50b71-108">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="50b71-109">enuncia La matriz de eventos devueltos.</span><span class="sxs-lookup"><span data-stu-id="50b71-109">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="50b71-110">[in] Tamaño máximo de la matriz `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="50b71-110">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="50b71-111">enuncia Número real de eventos devueltos en `rEvents` .</span><span class="sxs-lookup"><span data-stu-id="50b71-111">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50b71-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="50b71-112">Return Value</span></span>  
  
|<span data-ttu-id="50b71-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50b71-113">HRESULT</span></span>|<span data-ttu-id="50b71-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="50b71-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="50b71-115">`EnumEvents` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="50b71-115">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="50b71-116">No hay eventos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="50b71-116">There are no events to enumerate.</span></span> <span data-ttu-id="50b71-117">En ese caso, `pcEvents` es cero.</span><span class="sxs-lookup"><span data-stu-id="50b71-117">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50b71-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50b71-118">Requirements</span></span>  

 <span data-ttu-id="50b71-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50b71-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50b71-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="50b71-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50b71-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="50b71-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50b71-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50b71-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b71-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b71-123">See also</span></span>

- [<span data-ttu-id="50b71-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50b71-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="50b71-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50b71-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
