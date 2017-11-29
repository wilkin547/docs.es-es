---
title: "IMetaDataEmit::DefineEvent (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf790ce270565abaf1d91e54c9e3569a50ab3435
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="aec24-102">IMetaDataEmit::DefineEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="aec24-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="aec24-103">Crea una definición para un evento con la firma de metadatos especificada y obtiene un símbolo (token) para dicha definición de evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aec24-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="aec24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aec24-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="aec24-106">[in] El token para la interfaz o clase de destino.</span><span class="sxs-lookup"><span data-stu-id="aec24-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="aec24-107">Esto es un `mdTypeDef` o `mdTypeDefNil` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="aec24-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="aec24-108">[in] El nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="aec24-109">[in] Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="aec24-110">[in] El token para la clase de eventos.</span><span class="sxs-lookup"><span data-stu-id="aec24-110">[in] The token for the event class.</span></span> <span data-ttu-id="aec24-111">Se trata de un `mdTypeDef`, `mdTypeRef`, o un `mdTokenNil` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="aec24-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="aec24-112">[in] El método utilizado para suscribirse al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="aec24-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="aec24-113">[in] El método utilizado para cancelar la suscripción al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="aec24-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="aec24-114">[in] El método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="aec24-115">[in] Una matriz de símbolos (tokens) de otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="aec24-116">La matriz termina con un `mdMethodDefNil` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="aec24-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="aec24-117">[out] El token de metadatos asignado al evento.</span><span class="sxs-lookup"><span data-stu-id="aec24-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec24-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aec24-118">Requirements</span></span>  
 <span data-ttu-id="aec24-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec24-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec24-120">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aec24-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aec24-121">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aec24-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aec24-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec24-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec24-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec24-123">See Also</span></span>  
 [<span data-ttu-id="aec24-124">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aec24-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="aec24-125">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aec24-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
