---
title: IMetaDataImport::IsValidToken (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
ms.openlocfilehash: b4dc1e60f3d29e2671882d1900a1c49e56969601
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702867"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="a79b3-102">IMetaDataImport::IsValidToken (Método)</span><span class="sxs-lookup"><span data-stu-id="a79b3-102">IMetaDataImport::IsValidToken Method</span></span>

<span data-ttu-id="a79b3-103">Obtiene un valor que indica si el token especificado contiene una referencia válida a un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="a79b3-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a79b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a79b3-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a79b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a79b3-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="a79b3-106">de Token para el que se va a comprobar la validez de la referencia.</span><span class="sxs-lookup"><span data-stu-id="a79b3-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a79b3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a79b3-107">Return Value</span></span>  

 <span data-ttu-id="a79b3-108">`true` Si `tk` es un token de metadatos válido dentro del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="a79b3-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="a79b3-109">En caso contrario, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a79b3-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a79b3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a79b3-110">Requirements</span></span>  

 <span data-ttu-id="a79b3-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a79b3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a79b3-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a79b3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a79b3-113">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a79b3-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a79b3-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a79b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a79b3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a79b3-115">See also</span></span>

- [<span data-ttu-id="a79b3-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a79b3-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a79b3-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a79b3-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
