---
title: IMetaDataEmit::Save (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e45085b0fbca10e490f11ce588f68aa8237b46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139079"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="24a09-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="24a09-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="24a09-103">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="24a09-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24a09-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24a09-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24a09-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="24a09-106">[in] El nombre del archivo que se guarde en.</span><span class="sxs-lookup"><span data-stu-id="24a09-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="24a09-107">Si este valor es null, la copia en memoria se guardará a la última ubicación que se usó.</span><span class="sxs-lookup"><span data-stu-id="24a09-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="24a09-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="24a09-108">[in] Reserved.</span></span> <span data-ttu-id="24a09-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="24a09-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24a09-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24a09-110">Requirements</span></span>  
 <span data-ttu-id="24a09-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24a09-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a09-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="24a09-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24a09-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24a09-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="24a09-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="24a09-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24a09-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="24a09-115">See also</span></span>

- [<span data-ttu-id="24a09-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24a09-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="24a09-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24a09-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
