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
ms.openlocfilehash: 34db47b9f43412c9b6c5f58dd6afded505703905
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445382"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="ce16a-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="ce16a-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="ce16a-103">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ce16a-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce16a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce16a-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce16a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce16a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ce16a-106">[in] Un `mdFieldDef` o `mdMethodDef` símbolo (token) que representa el objeto para el que se va a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ce16a-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce16a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce16a-107">Requirements</span></span>  
 <span data-ttu-id="ce16a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce16a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce16a-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce16a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce16a-110">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce16a-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce16a-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce16a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce16a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce16a-112">See Also</span></span>  
 [<span data-ttu-id="ce16a-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce16a-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ce16a-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce16a-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
