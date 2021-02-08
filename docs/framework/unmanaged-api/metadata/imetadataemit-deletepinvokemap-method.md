---
description: 'Más información acerca de: IMetaDataEmit::D método eletePinvokeMap'
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
ms.openlocfilehash: 977fd600600cdfba0fd9fd5d383648ffbf63229f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783981"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="a6213-103">IMetaDataEmit::DeletePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="a6213-103">IMetaDataEmit::DeletePinvokeMap Method</span></span>

<span data-ttu-id="a6213-104">Destruye los metadatos de asignación de PInvoke para el objeto al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="a6213-104">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6213-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6213-105">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6213-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6213-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="a6213-107">de Un `mdFieldDef` `mdMethodDef` token o que representa el objeto para el que se van a eliminar los metadatos de asignación de PInvoke.</span><span class="sxs-lookup"><span data-stu-id="a6213-107">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6213-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6213-108">Requirements</span></span>  

 <span data-ttu-id="a6213-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6213-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6213-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6213-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6213-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6213-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6213-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6213-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6213-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6213-113">See also</span></span>

- [<span data-ttu-id="a6213-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6213-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a6213-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6213-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
