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
ms.openlocfilehash: 720133e64c02aa09c9ff7e43a20630b0d55c1acf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008760"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="55030-102">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="55030-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="55030-103">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="55030-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55030-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55030-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="55030-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55030-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="55030-106">de El token del evento.</span><span class="sxs-lookup"><span data-stu-id="55030-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="55030-107">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="55030-107">[in] Event flags.</span></span> <span data-ttu-id="55030-108">Se trata de una máscara de máscara de `CorEventAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="55030-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="55030-109">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="55030-109">[in] The token for the event class.</span></span> <span data-ttu-id="55030-110">Este es un `mdTypeDef` `mdTypeRef` token o.</span><span class="sxs-lookup"><span data-stu-id="55030-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="55030-111">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="55030-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="55030-112">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="55030-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="55030-113">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="55030-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="55030-114">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="55030-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="55030-115">El último elemento de la matriz debe ser `mdMethodDefNil` .</span><span class="sxs-lookup"><span data-stu-id="55030-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55030-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55030-116">Requirements</span></span>  
 <span data-ttu-id="55030-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55030-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55030-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="55030-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55030-119">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55030-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55030-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55030-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55030-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55030-121">See also</span></span>

- [<span data-ttu-id="55030-122">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55030-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="55030-123">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55030-123">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
