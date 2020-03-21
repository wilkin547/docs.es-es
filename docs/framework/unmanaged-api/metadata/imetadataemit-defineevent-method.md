---
title: IMetaDataEmit::DefineEvent (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175855"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="120c9-102">IMetaDataEmit::DefineEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="120c9-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="120c9-103">Crea una definición para un evento con la firma de metadatos especificada y obtiene un token a esa definición de evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="120c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="120c9-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="120c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="120c9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="120c9-106">[en] El token para la clase o interfaz de destino.</span><span class="sxs-lookup"><span data-stu-id="120c9-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="120c9-107">Esto es `mdTypeDef` un `mdTypeDefNil` token o un token.</span><span class="sxs-lookup"><span data-stu-id="120c9-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="120c9-108">[in] Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="120c9-109">[en] Indicadores de eventos.</span><span class="sxs-lookup"><span data-stu-id="120c9-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="120c9-110">[en] El token de la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-110">[in] The token for the event class.</span></span> <span data-ttu-id="120c9-111">Se trata `mdTypeDef`de `mdTypeRef`un `mdTokenNil` token , a o un token.</span><span class="sxs-lookup"><span data-stu-id="120c9-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="120c9-112">[en] El método utilizado para suscribirse al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="120c9-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="120c9-113">[en] El método utilizado para cancelar la suscripción al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="120c9-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="120c9-114">[en] El método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="120c9-115">[en] Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="120c9-116">La matriz se termina `mdMethodDefNil` con un token.</span><span class="sxs-lookup"><span data-stu-id="120c9-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="120c9-117">[fuera] El token de metadatos asignado al evento.</span><span class="sxs-lookup"><span data-stu-id="120c9-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="120c9-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="120c9-118">Requirements</span></span>  
 <span data-ttu-id="120c9-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="120c9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="120c9-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="120c9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="120c9-121">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="120c9-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="120c9-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="120c9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="120c9-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="120c9-123">See also</span></span>

- [<span data-ttu-id="120c9-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="120c9-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="120c9-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="120c9-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
