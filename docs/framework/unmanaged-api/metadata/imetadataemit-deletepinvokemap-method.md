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
ms.openlocfilehash: 45f40dcd419e8e2fdf8a3349ccc9461854ad9aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175738"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="ebd3b-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="ebd3b-103">Destruye los metadatos de asignación PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebd3b-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebd3b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebd3b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ebd3b-106">[en] Un `mdFieldDef` `mdMethodDef` token que representa el objeto para el que se va a eliminar los metadatos de asignación PInvoke.</span><span class="sxs-lookup"><span data-stu-id="ebd3b-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebd3b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebd3b-107">Requirements</span></span>  
 <span data-ttu-id="ebd3b-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebd3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebd3b-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ebd3b-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebd3b-110">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebd3b-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebd3b-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd3b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd3b-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebd3b-112">See also</span></span>

- [<span data-ttu-id="ebd3b-113">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ebd3b-114">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebd3b-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
