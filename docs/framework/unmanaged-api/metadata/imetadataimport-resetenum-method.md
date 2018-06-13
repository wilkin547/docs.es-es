---
title: IMetaDataImport::ResetEnum (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56fc0273fb2c1b77c74d7a1d853886f47170497e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447933"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="03be4-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="03be4-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="03be4-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="03be4-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03be4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03be4-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03be4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03be4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="03be4-106">[in] Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="03be4-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="03be4-107">[in] La nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="03be4-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03be4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03be4-108">Requirements</span></span>  
 <span data-ttu-id="03be4-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03be4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03be4-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03be4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03be4-111">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03be4-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03be4-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03be4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03be4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="03be4-113">See Also</span></span>  
 [<span data-ttu-id="03be4-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03be4-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="03be4-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03be4-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
