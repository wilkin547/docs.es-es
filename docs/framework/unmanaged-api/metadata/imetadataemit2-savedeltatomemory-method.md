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
ms.openlocfilehash: f8cc9544279c6be3efe278c3effda00bc2d387ec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495369"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="d2fcd-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="d2fcd-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="d2fcd-103">Guarda los cambios de la sesión actual de editar y continuar en la memoria.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2fcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2fcd-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2fcd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2fcd-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="d2fcd-106">[out] La dirección en que se va a empezar a escribir el delta de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d2fcd-107">[in] El tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-107">[in] The size of the changes.</span></span> <span data-ttu-id="d2fcd-108">Use [Imetadataemit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="d2fcd-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2fcd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2fcd-109">Requirements</span></span>  
 <span data-ttu-id="d2fcd-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2fcd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2fcd-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2fcd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2fcd-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2fcd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d2fcd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2fcd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2fcd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2fcd-114">See also</span></span>
- [<span data-ttu-id="d2fcd-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2fcd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d2fcd-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2fcd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
