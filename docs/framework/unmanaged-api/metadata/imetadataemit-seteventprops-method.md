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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450319"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="847c0-102">IMetaDataEmit::SetEventProps (Método)</span><span class="sxs-lookup"><span data-stu-id="847c0-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="847c0-103">Establece o actualiza la característica especificada de un evento definido por una llamada anterior a [IMetaDataEmit::D efineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="847c0-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="847c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="847c0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="847c0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="847c0-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="847c0-106">de El token del evento.</span><span class="sxs-lookup"><span data-stu-id="847c0-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="847c0-107">de Marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="847c0-107">[in] Event flags.</span></span> <span data-ttu-id="847c0-108">Se trata de una máscara de máscara de valores `CorEventAttr`.</span><span class="sxs-lookup"><span data-stu-id="847c0-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="847c0-109">de El token para la clase de evento.</span><span class="sxs-lookup"><span data-stu-id="847c0-109">[in] The token for the event class.</span></span> <span data-ttu-id="847c0-110">Se trata de un `mdTypeDef` o un token de `mdTypeRef`.</span><span class="sxs-lookup"><span data-stu-id="847c0-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="847c0-111">de Método utilizado para suscribirse al evento o null.</span><span class="sxs-lookup"><span data-stu-id="847c0-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="847c0-112">de Método utilizado para cancelar la suscripción al evento o null.</span><span class="sxs-lookup"><span data-stu-id="847c0-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="847c0-113">de Método utilizado (por una clase derivada) para generar el evento.</span><span class="sxs-lookup"><span data-stu-id="847c0-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="847c0-114">de Matriz de tokens para otros métodos asociados al evento.</span><span class="sxs-lookup"><span data-stu-id="847c0-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="847c0-115">El último elemento de la matriz se debe `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="847c0-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="847c0-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="847c0-116">Requirements</span></span>  
 <span data-ttu-id="847c0-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="847c0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="847c0-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="847c0-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="847c0-119">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="847c0-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="847c0-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="847c0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="847c0-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="847c0-121">See also</span></span>

- [<span data-ttu-id="847c0-122">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="847c0-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="847c0-123">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="847c0-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
