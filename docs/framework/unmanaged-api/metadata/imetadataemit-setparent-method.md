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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175608"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="f5211-102">IMetaDataEmit::SetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="f5211-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="f5211-103">Establece que el miembro especificado, tal como se define mediante una llamada anterior a [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define mediante una llamada anterior a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5211-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5211-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5211-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5211-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5211-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="f5211-106">[en] El `mdMemberRef` token para recibir un nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="f5211-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="f5211-107">[en] El `mdToken` para el nuevo padre.</span><span class="sxs-lookup"><span data-stu-id="f5211-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5211-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5211-108">Requirements</span></span>  
 <span data-ttu-id="f5211-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5211-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5211-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5211-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5211-111">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5211-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5211-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5211-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5211-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5211-113">See also</span></span>

- [<span data-ttu-id="f5211-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5211-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f5211-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5211-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
