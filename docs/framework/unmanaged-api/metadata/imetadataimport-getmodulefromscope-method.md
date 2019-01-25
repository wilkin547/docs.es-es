---
title: IMetaDataImport::GetModuleFromScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 931b17858465d4ff380069fc2cf2bb37cb7a7ffc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718187"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="f024e-102">IMetaDataImport::GetModuleFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="f024e-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="f024e-103">Obtiene los metadatos de un token para el módulo hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f024e-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f024e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f024e-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f024e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f024e-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="f024e-106">[out] Un puntero al token que representa el módulo hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f024e-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f024e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f024e-107">Requirements</span></span>  
 <span data-ttu-id="f024e-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f024e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f024e-109">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f024e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f024e-110">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f024e-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f024e-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f024e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f024e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f024e-112">See also</span></span>
- [<span data-ttu-id="f024e-113">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f024e-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f024e-114">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f024e-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
