---
description: 'Más información acerca de: IMetaDataEmit::D método efineEvent'
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
ms.openlocfilehash: f96f3a5b2ed16ba83223312af82cac7688cebfa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753476"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="9c99b-103">IMetaDataEmit::DefineEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="9c99b-103">IMetaDataEmit::DefineEvent Method</span></span>

<span data-ttu-id="9c99b-104">Crea una definición para un evento con la firma de metadatos especificada y obtiene un token para esa definición de evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-104">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c99b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c99b-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9c99b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c99b-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="9c99b-107">de Token de la clase o interfaz de destino.</span><span class="sxs-lookup"><span data-stu-id="9c99b-107">[in] The token for the target class or interface.</span></span> <span data-ttu-id="9c99b-108">Este es un `mdTypeDef` token o `mdTypeDefNil` .</span><span class="sxs-lookup"><span data-stu-id="9c99b-108">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="9c99b-109">[in] Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-109">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="9c99b-110">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-110">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="9c99b-111">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-111">[in] The token for the event class.</span></span> <span data-ttu-id="9c99b-112">Se trata de un `mdTypeDef` , un `mdTypeRef` o un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="9c99b-112">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="9c99b-113">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="9c99b-113">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="9c99b-114">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="9c99b-114">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="9c99b-115">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-115">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="9c99b-116">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-116">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="9c99b-117">La matriz se termina con un `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="9c99b-117">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="9c99b-118">enuncia Símbolo (token) de metadatos asignado al evento.</span><span class="sxs-lookup"><span data-stu-id="9c99b-118">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c99b-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c99b-119">Requirements</span></span>  

 <span data-ttu-id="9c99b-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c99b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c99b-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9c99b-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9c99b-122">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c99b-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c99b-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c99b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c99b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c99b-124">See also</span></span>

- [<span data-ttu-id="9c99b-125">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c99b-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9c99b-126">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c99b-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
