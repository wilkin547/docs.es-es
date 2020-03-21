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
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177525"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="2eb31-102">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="2eb31-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="2eb31-103">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="2eb31-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2eb31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2eb31-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2eb31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2eb31-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="2eb31-106">[en] El token de evento.</span><span class="sxs-lookup"><span data-stu-id="2eb31-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="2eb31-107">[en] Indicadores de eventos.</span><span class="sxs-lookup"><span data-stu-id="2eb31-107">[in] Event flags.</span></span> <span data-ttu-id="2eb31-108">Esta es una `CorEventAttr` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="2eb31-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="2eb31-109">[en] El token de la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="2eb31-109">[in] The token for the event class.</span></span> <span data-ttu-id="2eb31-110">Esto es `mdTypeDef` un `mdTypeRef` token o un token.</span><span class="sxs-lookup"><span data-stu-id="2eb31-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="2eb31-111">[en] El método utilizado para suscribirse al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="2eb31-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="2eb31-112">[en] El método utilizado para cancelar la suscripción al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="2eb31-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="2eb31-113">[en] El método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="2eb31-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="2eb31-114">[en] Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="2eb31-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="2eb31-115">El último elemento de `mdMethodDefNil`la matriz debe ser .</span><span class="sxs-lookup"><span data-stu-id="2eb31-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2eb31-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2eb31-116">Requirements</span></span>  
 <span data-ttu-id="2eb31-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2eb31-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2eb31-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2eb31-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2eb31-119">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2eb31-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2eb31-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2eb31-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2eb31-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2eb31-121">See also</span></span>

- [<span data-ttu-id="2eb31-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2eb31-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2eb31-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2eb31-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
