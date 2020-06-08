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
ms.openlocfilehash: 53b1234a176cade5876d70da0cb4eadc18802c69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492309"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="9d889-102">IMetaDataImport::EnumEvents (Método)</span><span class="sxs-lookup"><span data-stu-id="9d889-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="9d889-103">Enumera los tokens de definición de eventos del token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="9d889-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d889-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d889-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d889-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d889-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9d889-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="9d889-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="9d889-107">de El token de TypeDef cuyas definiciones de evento se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="9d889-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="9d889-108">enuncia La matriz de eventos devueltos.</span><span class="sxs-lookup"><span data-stu-id="9d889-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9d889-109">[in] Tamaño máximo de la matriz `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="9d889-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="9d889-110">enuncia Número real de eventos devueltos en `rEvents` .</span><span class="sxs-lookup"><span data-stu-id="9d889-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d889-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d889-111">Return Value</span></span>  
  
|<span data-ttu-id="9d889-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d889-112">HRESULT</span></span>|<span data-ttu-id="9d889-113">Description</span><span class="sxs-lookup"><span data-stu-id="9d889-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9d889-114">`EnumEvents`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d889-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9d889-115">No hay eventos que enumerar.</span><span class="sxs-lookup"><span data-stu-id="9d889-115">There are no events to enumerate.</span></span> <span data-ttu-id="9d889-116">En ese caso, `pcEvents` es cero.</span><span class="sxs-lookup"><span data-stu-id="9d889-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d889-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d889-117">Requirements</span></span>  
 <span data-ttu-id="9d889-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d889-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d889-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9d889-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d889-120">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d889-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d889-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d889-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d889-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9d889-122">See also</span></span>

- [<span data-ttu-id="9d889-123">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d889-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="9d889-124">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d889-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
