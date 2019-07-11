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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753449924f3415eb826b59d3a887eb69b9efba39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778786"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="16e93-102">IMetaDataImport::IsValidToken (Método)</span><span class="sxs-lookup"><span data-stu-id="16e93-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="16e93-103">Obtiene un valor que indica si el token especificado contiene una referencia válida a un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="16e93-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16e93-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16e93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16e93-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="16e93-106">[in] Para comprobar la validez de referencia para el token.</span><span class="sxs-lookup"><span data-stu-id="16e93-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16e93-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="16e93-107">Return Value</span></span>  
 <span data-ttu-id="16e93-108">`true` Si `tk` es un token de metadatos válido dentro del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="16e93-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="16e93-109">En caso contrario, es `false`.</span><span class="sxs-lookup"><span data-stu-id="16e93-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16e93-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16e93-110">Requirements</span></span>  
 <span data-ttu-id="16e93-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16e93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16e93-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="16e93-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="16e93-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="16e93-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="16e93-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16e93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16e93-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="16e93-115">See also</span></span>

- [<span data-ttu-id="16e93-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16e93-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="16e93-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="16e93-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
