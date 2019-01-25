---
title: IMetaDataEmit::SaveToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3ef09c98f22b03a9c4473505605f1688d4bbf17
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612234"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="47f51-102">IMetaDataEmit::SaveToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="47f51-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="47f51-103">Guarda todos los metadatos en el ámbito actual en el área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="47f51-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f51-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47f51-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47f51-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47f51-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="47f51-106">[out] La dirección donde se comienzan a escribir metadatos.</span><span class="sxs-lookup"><span data-stu-id="47f51-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="47f51-107">[in] El tamaño, en bytes, de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="47f51-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f51-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47f51-108">Requirements</span></span>  
 <span data-ttu-id="47f51-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47f51-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f51-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="47f51-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47f51-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="47f51-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47f51-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47f51-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f51-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="47f51-113">See also</span></span>
- [<span data-ttu-id="47f51-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47f51-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="47f51-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47f51-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
