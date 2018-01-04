---
title: "IMetaDataImport::GetModuleFromScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b389df634a69bff6197ae11dea96fbb6344dd369
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="71e2f-102">IMetaDataImport::GetModuleFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="71e2f-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="71e2f-103">Obtiene metadatos de un símbolo (token) para el módulo al que hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="71e2f-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71e2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71e2f-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71e2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71e2f-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="71e2f-106">[out] Un puntero al token que representa el módulo al que hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="71e2f-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71e2f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71e2f-107">Requirements</span></span>  
 <span data-ttu-id="71e2f-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71e2f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71e2f-109">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71e2f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71e2f-110">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71e2f-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71e2f-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71e2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e2f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="71e2f-112">See Also</span></span>  
 [<span data-ttu-id="71e2f-113">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71e2f-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="71e2f-114">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="71e2f-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
