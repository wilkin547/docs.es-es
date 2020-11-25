---
title: IMetaDataEmit::SetEventProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: 5c2880ac07f0317bc36ff4bbde68cd3a25febf52
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721990"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="ad77a-102">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ad77a-102">IMetaDataEmit::SetEventProps Method</span></span>

<span data-ttu-id="ad77a-103">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad77a-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad77a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad77a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad77a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad77a-105">Parameters</span></span>  

 `ev`  
 <span data-ttu-id="ad77a-106">de El token del evento.</span><span class="sxs-lookup"><span data-stu-id="ad77a-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="ad77a-107">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="ad77a-107">[in] Event flags.</span></span> <span data-ttu-id="ad77a-108">Se trata de una máscara de máscara de `CorEventAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="ad77a-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="ad77a-109">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="ad77a-109">[in] The token for the event class.</span></span> <span data-ttu-id="ad77a-110">Este es un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="ad77a-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="ad77a-111">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="ad77a-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="ad77a-112">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="ad77a-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="ad77a-113">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="ad77a-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="ad77a-114">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="ad77a-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="ad77a-115">El último elemento de la matriz debe ser `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="ad77a-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad77a-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad77a-116">Requirements</span></span>  

 <span data-ttu-id="ad77a-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad77a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad77a-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad77a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad77a-119">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad77a-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad77a-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad77a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad77a-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ad77a-121">See also</span></span>

- [<span data-ttu-id="ad77a-122">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad77a-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ad77a-123">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad77a-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
