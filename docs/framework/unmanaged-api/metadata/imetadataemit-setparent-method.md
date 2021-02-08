---
description: 'Más información acerca de: IMetaDataEmit:: SetParent (método)'
title: IMetaDataEmit::SetParent (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: 9025d4a37de85a0e657059f63ef781dc4377c036
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772008"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="60b1d-103">IMetaDataEmit::SetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="60b1d-103">IMetaDataEmit::SetParent Method</span></span>

<span data-ttu-id="60b1d-104">Establece que el miembro especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="60b1d-104">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60b1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60b1d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60b1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60b1d-106">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="60b1d-107">de El `mdMemberRef` token para recibir un nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="60b1d-107">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="60b1d-108">de `mdToken` Para el nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="60b1d-108">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60b1d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60b1d-109">Requirements</span></span>  

 <span data-ttu-id="60b1d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60b1d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60b1d-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="60b1d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="60b1d-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60b1d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60b1d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60b1d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b1d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="60b1d-114">See also</span></span>

- [<span data-ttu-id="60b1d-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60b1d-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="60b1d-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60b1d-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
