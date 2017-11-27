---
title: "IMetaDataImport::ResetEnum (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResetEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2cdb4c00185d152be856a99e1fec9392fd2a4029
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="007b6-102">IMetaDataImport::ResetEnum (Método)</span><span class="sxs-lookup"><span data-stu-id="007b6-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="007b6-103">Restablece el enumerador especificado a la posición especificada.</span><span class="sxs-lookup"><span data-stu-id="007b6-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="007b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="007b6-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="007b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="007b6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="007b6-106">[in] Enumerador que se va a restablecer.</span><span class="sxs-lookup"><span data-stu-id="007b6-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="007b6-107">[in] La nueva posición en la que se va a colocar el enumerador.</span><span class="sxs-lookup"><span data-stu-id="007b6-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="007b6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="007b6-108">Requirements</span></span>  
 <span data-ttu-id="007b6-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="007b6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="007b6-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="007b6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="007b6-111">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="007b6-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="007b6-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="007b6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="007b6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="007b6-113">See Also</span></span>  
 [<span data-ttu-id="007b6-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="007b6-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="007b6-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="007b6-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
