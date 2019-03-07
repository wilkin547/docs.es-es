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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26fd4c89838912e4e07c1d9a8b84aa22f54adeff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501635"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="f2c02-102">IMetaDataEmit::DefineEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="f2c02-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="f2c02-103">Crea una definición para un evento con la firma de metadatos especificados y obtiene un token para esa definición de evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2c02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2c02-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="f2c02-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2c02-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f2c02-106">[in] El token para la interfaz o clase de destino.</span><span class="sxs-lookup"><span data-stu-id="f2c02-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="f2c02-107">Puede ser un `mdTypeDef` o `mdTypeDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="f2c02-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="f2c02-108">[in] El nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="f2c02-109">[in] Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="f2c02-110">[in] El token para la clase de eventos.</span><span class="sxs-lookup"><span data-stu-id="f2c02-110">[in] The token for the event class.</span></span> <span data-ttu-id="f2c02-111">Se trata de un `mdTypeDef`, un `mdTypeRef`, o un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="f2c02-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="f2c02-112">[in] El método utilizado para suscribirse al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="f2c02-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="f2c02-113">[in] El método utilizado para cancelar la suscripción al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="f2c02-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="f2c02-114">[in] El método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="f2c02-115">[in] Una matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="f2c02-116">La matriz se termina con un `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="f2c02-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="f2c02-117">[out] El token de metadatos asignado al evento.</span><span class="sxs-lookup"><span data-stu-id="f2c02-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2c02-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2c02-118">Requirements</span></span>  
 <span data-ttu-id="f2c02-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2c02-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2c02-120">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2c02-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2c02-121">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2c02-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2c02-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2c02-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c02-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2c02-123">See also</span></span>
- [<span data-ttu-id="f2c02-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2c02-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f2c02-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2c02-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
