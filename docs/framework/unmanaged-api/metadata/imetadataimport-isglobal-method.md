---
description: 'Más información sobre: IMetaDataImport:: ISGlobal ((método)'
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
ms.openlocfilehash: 5230b2967990e3c52b429d62dd03566c3043e45f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789078"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="57113-103">IMetaDataImport::IsGlobal (Método)</span><span class="sxs-lookup"><span data-stu-id="57113-103">IMetaDataImport::IsGlobal Method</span></span>

<span data-ttu-id="57113-104">Obtiene un valor que indica si el campo, el método o el tipo representado por el token de metadatos especificado es de ámbito global.</span><span class="sxs-lookup"><span data-stu-id="57113-104">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57113-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57113-105">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57113-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57113-106">Parameters</span></span>  

 `pd`  
 <span data-ttu-id="57113-107">de Token de metadatos que representa un tipo, campo o método.</span><span class="sxs-lookup"><span data-stu-id="57113-107">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="57113-108">[out] 1 si el objeto tiene ámbito global; de lo contrario, 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="57113-108">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57113-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57113-109">Requirements</span></span>  

 <span data-ttu-id="57113-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57113-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57113-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57113-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57113-112">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57113-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57113-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57113-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57113-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="57113-114">See also</span></span>

- [<span data-ttu-id="57113-115">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57113-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="57113-116">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57113-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
