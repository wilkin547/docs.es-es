---
title: IMetaDataEmit::DeleteClassLayout (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 663f2de5acb3aac92c29a19f5f5db16b5355fe89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444788"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="b499b-102">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="b499b-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="b499b-103">Destruye la firma de metadatos del diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="b499b-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b499b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b499b-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b499b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b499b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b499b-106">[in] Un `mdTypeDef` símbolo (token) de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="b499b-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b499b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b499b-107">Requirements</span></span>  
 <span data-ttu-id="b499b-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b499b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b499b-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b499b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b499b-110">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b499b-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b499b-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b499b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b499b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b499b-112">See Also</span></span>  
 [<span data-ttu-id="b499b-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b499b-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b499b-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b499b-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
