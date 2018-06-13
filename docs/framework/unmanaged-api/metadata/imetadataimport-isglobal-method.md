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
ms.openlocfilehash: 4156c3507ccbd21d59893c5e03e15fe9b7322e48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447803"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="91af8-102">IMetaDataImport::IsGlobal (Método)</span><span class="sxs-lookup"><span data-stu-id="91af8-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="91af8-103">Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="91af8-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91af8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91af8-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91af8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91af8-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="91af8-106">[in] Símbolo (token) de metadatos que representa un tipo, campo o método.</span><span class="sxs-lookup"><span data-stu-id="91af8-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="91af8-107">[out] 1 si el objeto tiene ámbito global; en caso contrario, es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="91af8-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91af8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91af8-108">Requirements</span></span>  
 <span data-ttu-id="91af8-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91af8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91af8-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="91af8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91af8-111">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91af8-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91af8-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91af8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91af8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="91af8-113">See Also</span></span>  
 [<span data-ttu-id="91af8-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91af8-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="91af8-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="91af8-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
