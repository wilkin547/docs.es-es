---
title: IMetaDataEmit::DeletePinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3b7c116410ce3309d970929580f4ec7f65bd657
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558289"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="3b4c7-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="3b4c7-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="3b4c7-103">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b4c7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b4c7-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b4c7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b4c7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3b4c7-106">[in] Un `mdFieldDef` o `mdMethodDef` token que representa el objeto que se va a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="3b4c7-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b4c7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b4c7-107">Requirements</span></span>  
 <span data-ttu-id="3b4c7-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b4c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b4c7-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b4c7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b4c7-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3b4c7-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b4c7-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b4c7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b4c7-112">See also</span></span>
- [<span data-ttu-id="3b4c7-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b4c7-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b4c7-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b4c7-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
