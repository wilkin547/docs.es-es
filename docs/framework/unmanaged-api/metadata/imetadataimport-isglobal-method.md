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
ms.openlocfilehash: 8a5dda5861343865a139f6b6b9e2794179b0727a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434715"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="0f71c-102">IMetaDataImport::IsGlobal (Método)</span><span class="sxs-lookup"><span data-stu-id="0f71c-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="0f71c-103">Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="0f71c-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f71c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f71c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f71c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f71c-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="0f71c-106">de Token de metadatos que representa un tipo, campo o método.</span><span class="sxs-lookup"><span data-stu-id="0f71c-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="0f71c-107">[out] 1 si el objeto tiene ámbito global; de lo contrario, 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="0f71c-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f71c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f71c-108">Requirements</span></span>  
 <span data-ttu-id="0f71c-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f71c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f71c-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0f71c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f71c-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0f71c-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f71c-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f71c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f71c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f71c-113">See also</span></span>

- [<span data-ttu-id="0f71c-114">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f71c-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f71c-115">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f71c-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
