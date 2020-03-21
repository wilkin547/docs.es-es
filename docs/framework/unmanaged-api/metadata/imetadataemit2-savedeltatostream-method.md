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
ms.openlocfilehash: 7e8376f3a029b0e3ec51a1e7587dd14b3e7530ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177423"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="3f306-102">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="3f306-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="3f306-103">Guarda los cambios de la sesión de edición y continuación actual en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="3f306-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f306-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f306-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f306-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f306-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="3f306-106">[en] Un puntero de interfaz a la secuencia grabable en la que se pueden guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="3f306-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="3f306-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="3f306-107">[in] Reserved.</span></span> <span data-ttu-id="3f306-108">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="3f306-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f306-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f306-109">Requirements</span></span>  
 <span data-ttu-id="3f306-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f306-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f306-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3f306-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f306-112">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f306-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f306-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f306-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f306-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3f306-114">See also</span></span>

- [<span data-ttu-id="3f306-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f306-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3f306-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f306-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
