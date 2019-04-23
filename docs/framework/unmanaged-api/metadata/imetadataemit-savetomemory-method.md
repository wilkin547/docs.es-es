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
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192113"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="1a292-102">IMetaDataEmit::SaveToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="1a292-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="1a292-103">Guarda todos los metadatos en el ámbito actual en el área de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="1a292-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a292-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a292-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a292-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a292-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="1a292-106">[out] La dirección donde se comienzan a escribir metadatos.</span><span class="sxs-lookup"><span data-stu-id="1a292-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="1a292-107">[in] El tamaño, en bytes, de la memoria asignada.</span><span class="sxs-lookup"><span data-stu-id="1a292-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a292-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a292-108">Requirements</span></span>  
 <span data-ttu-id="1a292-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a292-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a292-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a292-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a292-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a292-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a292-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a292-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a292-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a292-113">See also</span></span>

- [<span data-ttu-id="1a292-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a292-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1a292-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a292-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
