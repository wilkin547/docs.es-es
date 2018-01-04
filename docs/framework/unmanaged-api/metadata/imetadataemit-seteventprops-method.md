---
title: "IMetaDataEmit::SetEventProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8e2089c3f4b4e7677c2ddb9eabc8ee08cfd3695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="e33b9-102">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e33b9-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="e33b9-103">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit:: DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="e33b9-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e33b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e33b9-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="e33b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e33b9-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="e33b9-106">[in] El token de evento.</span><span class="sxs-lookup"><span data-stu-id="e33b9-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="e33b9-107">[in] Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="e33b9-107">[in] Event flags.</span></span> <span data-ttu-id="e33b9-108">Se trata de una máscara de bits de `CorEventAttr` valores.</span><span class="sxs-lookup"><span data-stu-id="e33b9-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="e33b9-109">[in] El token para la clase de eventos.</span><span class="sxs-lookup"><span data-stu-id="e33b9-109">[in] The token for the event class.</span></span> <span data-ttu-id="e33b9-110">Esto es un `mdTypeDef` o un `mdTypeRef` símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="e33b9-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="e33b9-111">[in] El método utilizado para suscribirse al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="e33b9-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="e33b9-112">[in] El método utilizado para cancelar la suscripción al evento, o null.</span><span class="sxs-lookup"><span data-stu-id="e33b9-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="e33b9-113">[in] El método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="e33b9-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e33b9-114">[in] Una matriz de símbolos (tokens) de otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="e33b9-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="e33b9-115">El último elemento de la matriz debe ser `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="e33b9-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e33b9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e33b9-116">Requirements</span></span>  
 <span data-ttu-id="e33b9-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e33b9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e33b9-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e33b9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e33b9-119">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e33b9-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e33b9-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e33b9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33b9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e33b9-121">See Also</span></span>  
 [<span data-ttu-id="e33b9-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e33b9-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e33b9-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e33b9-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
