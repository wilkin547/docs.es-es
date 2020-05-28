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
ms.openlocfilehash: def77bb64e21b1421983cf263d488ecc1ddb9452
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009330"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="8c981-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="8c981-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="8c981-103">Obtiene un símbolo (token) de metadatos para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="8c981-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c981-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c981-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c981-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c981-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="8c981-106">de Cadena de usuario que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="8c981-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="8c981-107">de Recuento de caracteres anchos en `szString` .</span><span class="sxs-lookup"><span data-stu-id="8c981-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="8c981-108">enuncia El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="8c981-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c981-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c981-109">Requirements</span></span>  
 <span data-ttu-id="8c981-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c981-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c981-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8c981-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c981-112">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c981-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c981-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c981-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c981-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8c981-114">See also</span></span>

- [<span data-ttu-id="8c981-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c981-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8c981-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c981-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
