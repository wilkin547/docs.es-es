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
ms.openlocfilehash: 5ea100ff86286cb98db5aa9fa6f3c12f5d318a90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217749"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="e1cad-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="e1cad-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="e1cad-103">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="e1cad-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1cad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1cad-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1cad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1cad-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e1cad-106">[in] Un `mdFieldDef` o `mdMethodDef` token que representa el objeto que se va a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="e1cad-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1cad-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1cad-107">Requirements</span></span>  
 <span data-ttu-id="e1cad-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1cad-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1cad-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e1cad-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1cad-110">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1cad-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e1cad-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e1cad-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e1cad-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1cad-112">See also</span></span>

- [<span data-ttu-id="e1cad-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1cad-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e1cad-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e1cad-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
