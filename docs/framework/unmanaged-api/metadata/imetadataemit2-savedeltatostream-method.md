---
title: IMetaDataEmit2::SaveDeltaToStream (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: a8f46871dde4c664a502c261fc882f3badf0f362
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492767"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="fb81d-102">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="fb81d-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="fb81d-103">Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="fb81d-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb81d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb81d-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb81d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb81d-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="fb81d-106">de Puntero de interfaz a la secuencia de escritura en la que se van a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="fb81d-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="fb81d-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="fb81d-107">[in] Reserved.</span></span> <span data-ttu-id="fb81d-108">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="fb81d-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb81d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb81d-109">Requirements</span></span>  
 <span data-ttu-id="fb81d-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb81d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb81d-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb81d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb81d-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fb81d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb81d-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb81d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb81d-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="fb81d-114">See also</span></span>

- [<span data-ttu-id="fb81d-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb81d-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="fb81d-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb81d-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
