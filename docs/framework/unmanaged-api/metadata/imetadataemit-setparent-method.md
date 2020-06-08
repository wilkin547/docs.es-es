---
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
ms.openlocfilehash: d821413e67b36392d936499cd22f2e065f1556ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503853"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="74ae2-102">IMetaDataEmit::SetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="74ae2-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="74ae2-103">Establece que el miembro especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="74ae2-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ae2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74ae2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74ae2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74ae2-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="74ae2-106">de El `mdMemberRef` token para recibir un nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="74ae2-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="74ae2-107">de `mdToken`Para el nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="74ae2-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74ae2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74ae2-108">Requirements</span></span>  
 <span data-ttu-id="74ae2-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74ae2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74ae2-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74ae2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74ae2-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="74ae2-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74ae2-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74ae2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ae2-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="74ae2-113">See also</span></span>

- [<span data-ttu-id="74ae2-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74ae2-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="74ae2-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="74ae2-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
