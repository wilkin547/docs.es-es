---
title: "IMetaDataEmit::DeleteClassLayout (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a215ba1f468823a93c1515c4a3875764a6ba5bb2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="9803e-102">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="9803e-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="9803e-103">Destruye la firma de metadatos del diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="9803e-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9803e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9803e-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9803e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9803e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9803e-106">[in] Un `mdTypeDef` símbolo (token) de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="9803e-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9803e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9803e-107">Requirements</span></span>  
 <span data-ttu-id="9803e-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9803e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9803e-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9803e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9803e-110">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9803e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9803e-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9803e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9803e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9803e-112">See Also</span></span>  
 [<span data-ttu-id="9803e-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9803e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9803e-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9803e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
