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
ms.openlocfilehash: 8a6f11996425c92d9b0e3123ee2d3a064739454b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492769"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="b6d1e-102">IMetaDataEmit2::SaveDeltaToMemory (Método)</span><span class="sxs-lookup"><span data-stu-id="b6d1e-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="b6d1e-103">Guarda los cambios de la sesión de edición y continuación actual en la memoria.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6d1e-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6d1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6d1e-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="b6d1e-106">enuncia Dirección en la que se va a comenzar a escribir la diferencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="b6d1e-107">de Tamaño de los cambios.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-107">[in] The size of the changes.</span></span> <span data-ttu-id="b6d1e-108">Use [IMetaDataEmit2:: GetDeltaSaveSize (](imetadataemit2-getdeltasavesize-method.md) para determinar el tamaño.</span><span class="sxs-lookup"><span data-stu-id="b6d1e-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d1e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6d1e-109">Requirements</span></span>  
 <span data-ttu-id="b6d1e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d1e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d1e-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6d1e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6d1e-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6d1e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6d1e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d1e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d1e-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b6d1e-114">See also</span></span>

- [<span data-ttu-id="b6d1e-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6d1e-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="b6d1e-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6d1e-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
