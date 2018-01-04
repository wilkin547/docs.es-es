---
title: "IMetaDataEmit::DeletePinvokeMap (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DeletePinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1479c3fb19feec0e42ee4aec8544a35ce51350a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="fe78c-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="fe78c-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="fe78c-103">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="fe78c-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe78c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe78c-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe78c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe78c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="fe78c-106">[in] Un `mdFieldDef` o `mdMethodDef` símbolo (token) que representa el objeto para el que se va a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="fe78c-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe78c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe78c-107">Requirements</span></span>  
 <span data-ttu-id="fe78c-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe78c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe78c-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe78c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe78c-110">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe78c-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe78c-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe78c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe78c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe78c-112">See Also</span></span>  
 [<span data-ttu-id="fe78c-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe78c-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="fe78c-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe78c-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
