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
ms.openlocfilehash: a73afaebc2943190eeeee50367ecd31f1fb59df1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432441"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="47746-102">IMetaDataEmit::SetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="47746-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="47746-103">Establece que el miembro especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define en una llamada anterior a [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="47746-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47746-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47746-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47746-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47746-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="47746-106">de El token de `mdMemberRef` para recibir un nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="47746-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="47746-107">de `mdToken` del nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="47746-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47746-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47746-108">Requirements</span></span>  
 <span data-ttu-id="47746-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47746-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47746-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="47746-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47746-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="47746-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47746-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47746-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47746-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="47746-113">See also</span></span>

- [<span data-ttu-id="47746-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47746-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="47746-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47746-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
