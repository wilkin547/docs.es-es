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
ms.openlocfilehash: a6d97d3e4a93985f9b2de3ed9785eff5f7f46c36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444684"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="85db0-102">IMetaDataEmit::Save (Método)</span><span class="sxs-lookup"><span data-stu-id="85db0-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="85db0-103">Guarda todos los metadatos en el ámbito actual en el archivo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="85db0-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85db0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85db0-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85db0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85db0-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="85db0-106">[in] El nombre del archivo que se guarde en.</span><span class="sxs-lookup"><span data-stu-id="85db0-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="85db0-107">Si este valor es null, la copia en memoria se guardará a la última ubicación que se utilizó.</span><span class="sxs-lookup"><span data-stu-id="85db0-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="85db0-108">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="85db0-108">[in] Reserved.</span></span> <span data-ttu-id="85db0-109">Debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="85db0-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85db0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85db0-110">Requirements</span></span>  
 <span data-ttu-id="85db0-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85db0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85db0-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85db0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85db0-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85db0-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85db0-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85db0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85db0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="85db0-115">See Also</span></span>  
 [<span data-ttu-id="85db0-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85db0-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="85db0-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85db0-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
