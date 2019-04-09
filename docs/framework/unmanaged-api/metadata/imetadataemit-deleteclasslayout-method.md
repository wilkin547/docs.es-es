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
ms.openlocfilehash: a195daf2aa1b1c5a8f9c4335f7c4185f30093360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178534"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="accdf-102">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="accdf-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="accdf-103">Destruye la firma de metadatos de diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="accdf-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accdf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accdf-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accdf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accdf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="accdf-106">[in] Un `mdTypeDef` token de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="accdf-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accdf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accdf-107">Requirements</span></span>  
 <span data-ttu-id="accdf-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accdf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accdf-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="accdf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="accdf-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="accdf-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="accdf-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="accdf-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="accdf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="accdf-112">See also</span></span>

- [<span data-ttu-id="accdf-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="accdf-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="accdf-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="accdf-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
