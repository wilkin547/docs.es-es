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
ms.openlocfilehash: d477976952d2c1875a620d1397fd43e5c5e2836f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503476"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="c21d7-102">IMetaDataImport::IsGlobal (Método)</span><span class="sxs-lookup"><span data-stu-id="c21d7-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="c21d7-103">Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="c21d7-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c21d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c21d7-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c21d7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c21d7-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="c21d7-106">de Token de metadatos que representa un tipo, campo o método.</span><span class="sxs-lookup"><span data-stu-id="c21d7-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="c21d7-107">[out] 1 si el objeto tiene ámbito global; de lo contrario, 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="c21d7-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c21d7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c21d7-108">Requirements</span></span>  
 <span data-ttu-id="c21d7-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c21d7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c21d7-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c21d7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c21d7-111">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c21d7-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c21d7-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c21d7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21d7-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="c21d7-113">See also</span></span>

- [<span data-ttu-id="c21d7-114">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c21d7-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c21d7-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c21d7-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
