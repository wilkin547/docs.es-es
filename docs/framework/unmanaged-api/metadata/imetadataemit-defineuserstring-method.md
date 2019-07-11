---
title: IMetaDataEmit::DefineUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25e35fd9afd2ce4dc60e23ccd64e0630a008bf39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777434"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="8bab6-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="8bab6-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="8bab6-103">Obtiene los metadatos de un token para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="8bab6-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bab6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bab6-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bab6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bab6-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="8bab6-106">[in] Para almacenar la cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="8bab6-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="8bab6-107">[in] El recuento de caracteres anchos en `szString`.</span><span class="sxs-lookup"><span data-stu-id="8bab6-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="8bab6-108">[out] El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="8bab6-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bab6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bab6-109">Requirements</span></span>  
 <span data-ttu-id="8bab6-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bab6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bab6-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bab6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bab6-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bab6-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8bab6-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bab6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bab6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bab6-114">See also</span></span>

- [<span data-ttu-id="8bab6-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8bab6-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8bab6-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8bab6-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
