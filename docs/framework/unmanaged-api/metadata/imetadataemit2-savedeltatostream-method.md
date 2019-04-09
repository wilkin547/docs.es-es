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
ms.openlocfilehash: 31bed2019eef5a37e1086624afdae3e8f2c58632
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119215"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="199b7-102">IMetaDataEmit2::SaveDeltaToStream (Método)</span><span class="sxs-lookup"><span data-stu-id="199b7-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="199b7-103">Guarda los cambios de la sesión actual de editar y continuar en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="199b7-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199b7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="199b7-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="199b7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="199b7-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="199b7-106">[in] Un puntero de interfaz a la secuencia de escritura que se va a guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="199b7-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="199b7-107">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="199b7-107">[in] Reserved.</span></span> <span data-ttu-id="199b7-108">Este valor debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="199b7-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="199b7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="199b7-109">Requirements</span></span>  
 <span data-ttu-id="199b7-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="199b7-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="199b7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="199b7-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="199b7-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="199b7-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="199b7-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="199b7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="199b7-114">See also</span></span>

- [<span data-ttu-id="199b7-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="199b7-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="199b7-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="199b7-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
