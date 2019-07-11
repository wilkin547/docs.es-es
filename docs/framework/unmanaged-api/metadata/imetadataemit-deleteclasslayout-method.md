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
ms.openlocfilehash: 84de8e3c688a23198762fca5219d317fabb69c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777459"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="d3ad0-102">IMetaDataEmit::DeleteClassLayout (Método)</span><span class="sxs-lookup"><span data-stu-id="d3ad0-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="d3ad0-103">Destruye la firma de metadatos de diseño de clase para el tipo representado por el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d3ad0-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ad0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3ad0-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3ad0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d3ad0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d3ad0-106">[in] Un `mdTypeDef` token de metadatos que representa el tipo para el que se eliminará el diseño de clase.</span><span class="sxs-lookup"><span data-stu-id="d3ad0-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ad0-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3ad0-107">Requirements</span></span>  
 <span data-ttu-id="d3ad0-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3ad0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ad0-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3ad0-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3ad0-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d3ad0-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3ad0-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ad0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ad0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3ad0-112">See also</span></span>

- [<span data-ttu-id="d3ad0-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3ad0-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d3ad0-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3ad0-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
