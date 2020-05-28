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
ms.openlocfilehash: 7babd0a90b9882acb03b6360753f55c57a399b9e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005640"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="555aa-102">IMetaDataEmit::DefineEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="555aa-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="555aa-103">Crea una definición para un evento con la firma de metadatos especificada y obtiene un token para esa definición de evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="555aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="555aa-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="555aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="555aa-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="555aa-106">de Token de la clase o interfaz de destino.</span><span class="sxs-lookup"><span data-stu-id="555aa-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="555aa-107">Este es un `mdTypeDef` token o `mdTypeDefNil` .</span><span class="sxs-lookup"><span data-stu-id="555aa-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="555aa-108">[in] Nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="555aa-109">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="555aa-110">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-110">[in] The token for the event class.</span></span> <span data-ttu-id="555aa-111">Se trata de un `mdTypeDef` , un `mdTypeRef` o un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="555aa-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="555aa-112">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="555aa-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="555aa-113">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="555aa-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="555aa-114">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="555aa-115">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="555aa-116">La matriz se termina con un `mdMethodDefNil` token.</span><span class="sxs-lookup"><span data-stu-id="555aa-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="555aa-117">enuncia Símbolo (token) de metadatos asignado al evento.</span><span class="sxs-lookup"><span data-stu-id="555aa-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="555aa-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="555aa-118">Requirements</span></span>  
 <span data-ttu-id="555aa-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="555aa-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="555aa-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="555aa-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="555aa-121">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="555aa-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="555aa-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="555aa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="555aa-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="555aa-123">See also</span></span>

- [<span data-ttu-id="555aa-124">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="555aa-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="555aa-125">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="555aa-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
