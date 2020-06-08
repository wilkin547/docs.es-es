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
ms.openlocfilehash: 9190d021b801be951d214406dde7e6d76da15608
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503447"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="f105e-102">IMetaDataImport::IsValidToken (Método)</span><span class="sxs-lookup"><span data-stu-id="f105e-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="f105e-103">Obtiene un valor que indica si el token especificado contiene una referencia válida a un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="f105e-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f105e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f105e-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f105e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f105e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="f105e-106">de Token para el que se va a comprobar la validez de la referencia.</span><span class="sxs-lookup"><span data-stu-id="f105e-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f105e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f105e-107">Return Value</span></span>  
 <span data-ttu-id="f105e-108">`true`Si `tk` es un token de metadatos válido dentro del ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f105e-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="f105e-109">En caso contrario, es `false`.</span><span class="sxs-lookup"><span data-stu-id="f105e-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f105e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f105e-110">Requirements</span></span>  
 <span data-ttu-id="f105e-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f105e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f105e-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f105e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f105e-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f105e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f105e-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f105e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f105e-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f105e-115">See also</span></span>

- [<span data-ttu-id="f105e-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f105e-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f105e-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f105e-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
