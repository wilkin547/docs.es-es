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
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777434"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="b3273-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="b3273-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="b3273-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="b3273-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3273-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3273-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3273-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3273-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b3273-106">[in] Para restablecer el enumerador.</span><span class="sxs-lookup"><span data-stu-id="b3273-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="b3273-107">[in] Nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="b3273-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3273-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3273-108">Requirements</span></span>  
 <span data-ttu-id="b3273-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3273-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3273-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b3273-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3273-111">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3273-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b3273-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3273-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3273-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3273-113">See also</span></span>

- [<span data-ttu-id="b3273-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3273-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b3273-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3273-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
