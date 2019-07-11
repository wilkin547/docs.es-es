---
title: IMetaDataEmit::SetRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02331bb3b0c70b946eaa28c9cd316f109ac927b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777239"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="ef320-102">IMetaDataEmit::SetRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="ef320-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="ef320-103">Establece la dirección virtual relativa del método especificado.</span><span class="sxs-lookup"><span data-stu-id="ef320-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef320-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef320-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef320-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef320-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ef320-106">[in] El token para el método de destino o la implementación del método.</span><span class="sxs-lookup"><span data-stu-id="ef320-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="ef320-107">[in] La dirección del área del código o datos.</span><span class="sxs-lookup"><span data-stu-id="ef320-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef320-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef320-108">Requirements</span></span>  
 <span data-ttu-id="ef320-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef320-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef320-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef320-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef320-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef320-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef320-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef320-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef320-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef320-113">See also</span></span>

- [<span data-ttu-id="ef320-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef320-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ef320-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef320-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
