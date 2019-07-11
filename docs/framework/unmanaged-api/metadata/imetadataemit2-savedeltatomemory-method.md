---
title: IMetaDataEmit2::SaveDeltaToMemory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79b21613ba844ca4c749d9c04d75260e326e6512
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777127"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="988d3-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="988d3-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="988d3-103">Guarda los cambios de la sesión actual de editar y continuar en la memoria.</span><span class="sxs-lookup"><span data-stu-id="988d3-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="988d3-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="988d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="988d3-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="988d3-106">[out] La dirección en que se va a empezar a escribir el delta de metadatos.</span><span class="sxs-lookup"><span data-stu-id="988d3-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="988d3-107">[in] El tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="988d3-107">[in] The size of the changes.</span></span> <span data-ttu-id="988d3-108">Use [Imetadataemit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="988d3-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988d3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="988d3-109">Requirements</span></span>  
 <span data-ttu-id="988d3-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988d3-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="988d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="988d3-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="988d3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="988d3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988d3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="988d3-114">See also</span></span>

- [<span data-ttu-id="988d3-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="988d3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="988d3-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="988d3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
