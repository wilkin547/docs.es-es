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
ms.openlocfilehash: bb08bad82400523d82e4b8589acb2e74fbbd17d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603737"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="b2658-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="b2658-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="b2658-103">Obtiene los metadatos de un token para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="b2658-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2658-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2658-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2658-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2658-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="b2658-106">[in] Para almacenar la cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2658-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="b2658-107">[in] El recuento de caracteres anchos en `szString`.</span><span class="sxs-lookup"><span data-stu-id="b2658-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="b2658-108">[out] El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="b2658-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2658-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2658-109">Requirements</span></span>  
 <span data-ttu-id="b2658-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2658-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2658-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2658-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2658-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2658-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2658-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2658-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2658-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2658-114">See also</span></span>
- [<span data-ttu-id="b2658-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2658-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b2658-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2658-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
