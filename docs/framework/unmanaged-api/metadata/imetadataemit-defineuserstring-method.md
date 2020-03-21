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
ms.openlocfilehash: a71d8694ec8c5bd35ecd3e98ed32e05bc7b382fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177618"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="c37a3-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="c37a3-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="c37a3-103">Obtiene un token de metadatos para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="c37a3-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c37a3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c37a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c37a3-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="c37a3-106">[en] La cadena de usuario que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="c37a3-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="c37a3-107">[en] El recuento de `szString`caracteres anchos en .</span><span class="sxs-lookup"><span data-stu-id="c37a3-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="c37a3-108">[fuera] El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="c37a3-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37a3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c37a3-109">Requirements</span></span>  
 <span data-ttu-id="c37a3-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c37a3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37a3-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c37a3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c37a3-112">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c37a3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c37a3-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37a3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c37a3-114">See also</span></span>

- [<span data-ttu-id="c37a3-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37a3-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c37a3-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c37a3-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
