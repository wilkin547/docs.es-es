---
title: IMetaDataImport::IsGlobal (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b956ac1717ffcb73e819e985450249754f80af2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136167"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="433b3-102">IMetaDataImport::IsGlobal (Método)</span><span class="sxs-lookup"><span data-stu-id="433b3-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="433b3-103">Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="433b3-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="433b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="433b3-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="433b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="433b3-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="433b3-106">[in] Un token de metadatos que representa un tipo, campo o método.</span><span class="sxs-lookup"><span data-stu-id="433b3-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="433b3-107">[out] 1 si el objeto tiene ámbito global; en caso contrario, 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="433b3-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="433b3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="433b3-108">Requirements</span></span>  
 <span data-ttu-id="433b3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="433b3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="433b3-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="433b3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="433b3-111">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="433b3-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="433b3-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="433b3-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="433b3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="433b3-113">See also</span></span>

- [<span data-ttu-id="433b3-114">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433b3-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="433b3-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="433b3-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
