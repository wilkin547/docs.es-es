---
description: 'Más información sobre: IMetaDataEmit:: SetEventProps ((método)'
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
ms.openlocfilehash: 888999bc0f80e82e0d139eecac7152a94104ed7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658133"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="b4724-103">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="b4724-103">IMetaDataEmit::SetEventProps Method</span></span>

<span data-ttu-id="b4724-104">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4724-104">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4724-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4724-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4724-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4724-106">Parameters</span></span>  

 `ev`  
 <span data-ttu-id="b4724-107">de El token del evento.</span><span class="sxs-lookup"><span data-stu-id="b4724-107">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="b4724-108">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="b4724-108">[in] Event flags.</span></span> <span data-ttu-id="b4724-109">Se trata de una máscara de máscara de `CorEventAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="b4724-109">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="b4724-110">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="b4724-110">[in] The token for the event class.</span></span> <span data-ttu-id="b4724-111">Este es un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="b4724-111">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="b4724-112">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="b4724-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="b4724-113">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="b4724-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="b4724-114">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="b4724-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="b4724-115">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="b4724-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="b4724-116">El último elemento de la matriz debe ser `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="b4724-116">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4724-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4724-117">Requirements</span></span>  

 <span data-ttu-id="b4724-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4724-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4724-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4724-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4724-120">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4724-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4724-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4724-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4724-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4724-122">See also</span></span>

- [<span data-ttu-id="b4724-123">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4724-123">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b4724-124">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4724-124">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
