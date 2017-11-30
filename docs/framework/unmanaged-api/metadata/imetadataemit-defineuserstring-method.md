---
title: "IMetaDataEmit::DefineUserString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eb3e21e88da8fec08acf1ecbe451c5914b6cccaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="0a7c5-102">IMetaDataEmit::DefineUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="0a7c5-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="0a7c5-103">Obtiene metadatos de un símbolo (token) para la cadena literal especificada.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a7c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a7c5-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a7c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a7c5-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="0a7c5-106">[in] Para almacenar la cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="0a7c5-107">[in] El número de caracteres anchos en `szString`.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="0a7c5-108">[out] El token de cadena asignado.</span><span class="sxs-lookup"><span data-stu-id="0a7c5-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a7c5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a7c5-109">Requirements</span></span>  
 <span data-ttu-id="0a7c5-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a7c5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a7c5-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a7c5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a7c5-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a7c5-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a7c5-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a7c5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a7c5-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a7c5-114">See Also</span></span>  
 [<span data-ttu-id="0a7c5-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a7c5-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0a7c5-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a7c5-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
