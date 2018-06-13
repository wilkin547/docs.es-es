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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9dfd97ce5b9b192b9a2e88e3d7e4f963d929f47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449265"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="7c434-102">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="7c434-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="7c434-103">Guarda los cambios de la sesión actual de editar y continuar en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="7c434-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c434-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c434-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c434-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c434-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="7c434-106">[in] Un puntero de interfaz a la secuencia de escritura que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="7c434-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="7c434-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="7c434-107">[in] Reserved.</span></span> <span data-ttu-id="7c434-108">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="7c434-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c434-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c434-109">Requirements</span></span>  
 <span data-ttu-id="7c434-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c434-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c434-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c434-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c434-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c434-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c434-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c434-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c434-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c434-114">See Also</span></span>  
 [<span data-ttu-id="7c434-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c434-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="7c434-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c434-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
