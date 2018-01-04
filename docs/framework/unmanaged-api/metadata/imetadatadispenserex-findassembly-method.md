---
title: "IMetaDataDispenserEx::FindAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f125008e4ae5b7f2abbe6d467b486b962700d42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="30eb5-102">IMetaDataDispenserEx::FindAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="30eb5-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="30eb5-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="30eb5-103">This method is not implemented.</span></span> <span data-ttu-id="30eb5-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="30eb5-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30eb5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30eb5-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30eb5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30eb5-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="30eb5-107">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="30eb5-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="30eb5-108">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="30eb5-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="30eb5-109">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="30eb5-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="30eb5-110">[in] El ensamblado va a calcular.</span><span class="sxs-lookup"><span data-stu-id="30eb5-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="30eb5-111">[out] El nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="30eb5-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="30eb5-112">[in] El tamaño, en bytes, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="30eb5-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="30eb5-113">[out] El número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="30eb5-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30eb5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30eb5-114">Requirements</span></span>  
 <span data-ttu-id="30eb5-115">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30eb5-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30eb5-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="30eb5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30eb5-117">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30eb5-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30eb5-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30eb5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30eb5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="30eb5-119">See Also</span></span>  
 [<span data-ttu-id="30eb5-120">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30eb5-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="30eb5-121">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30eb5-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
