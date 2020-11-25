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
ms.openlocfilehash: 6fc6cf9b7333dd4caad3c5a4b081fecb060c8f86
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722094"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="4dba2-102">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="4dba2-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="4dba2-103">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="4dba2-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dba2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dba2-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dba2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4dba2-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="4dba2-106">de Un `mdFieldDef` `mdMethodDef` token o que representa el objeto para el que se van a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="4dba2-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dba2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dba2-107">Requirements</span></span>  

 <span data-ttu-id="4dba2-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dba2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dba2-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4dba2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4dba2-110">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4dba2-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dba2-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dba2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dba2-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dba2-112">See also</span></span>

- [<span data-ttu-id="4dba2-113">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4dba2-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4dba2-114">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4dba2-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
