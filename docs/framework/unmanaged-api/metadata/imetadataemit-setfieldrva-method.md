---
title: IMetaDataEmit::SetFieldRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a38de994575bf0191ff2ab5ce1c7b047540289f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470593"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="1bf9d-102">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="1bf9d-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="1bf9d-103">Establece un valor de la variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="1bf9d-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bf9d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bf9d-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bf9d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bf9d-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="1bf9d-106">[in] El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="1bf9d-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="1bf9d-107">[in] La dirección de un área de código o datos.</span><span class="sxs-lookup"><span data-stu-id="1bf9d-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bf9d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bf9d-108">Requirements</span></span>  
 <span data-ttu-id="1bf9d-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bf9d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bf9d-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1bf9d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bf9d-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bf9d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bf9d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bf9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf9d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bf9d-113">See also</span></span>
- [<span data-ttu-id="1bf9d-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bf9d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1bf9d-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bf9d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
