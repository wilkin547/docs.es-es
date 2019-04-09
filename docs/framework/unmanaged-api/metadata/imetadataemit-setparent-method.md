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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe27d8a0508a13c1f54eef00d5119bec4daec4a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140444"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="2ce7f-102">IMetaDataEmit::SetParent (Método)</span><span class="sxs-lookup"><span data-stu-id="2ce7f-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="2ce7f-103">Establece que el miembro especificado, tal como se define mediante una llamada anterior a [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), es un miembro del tipo especificado, tal como se define mediante una llamada anterior a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ce7f-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ce7f-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ce7f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ce7f-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="2ce7f-106">[in] El `mdMemberRef` símbolo (token) para recibir un nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="2ce7f-107">[in] El `mdToken` para el nuevo elemento primario.</span><span class="sxs-lookup"><span data-stu-id="2ce7f-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ce7f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ce7f-108">Requirements</span></span>  
 <span data-ttu-id="2ce7f-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ce7f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ce7f-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="2ce7f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ce7f-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ce7f-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2ce7f-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ce7f-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ce7f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ce7f-113">See also</span></span>

- [<span data-ttu-id="2ce7f-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ce7f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2ce7f-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ce7f-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
