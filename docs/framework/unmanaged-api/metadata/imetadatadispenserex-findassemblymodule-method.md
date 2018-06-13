---
title: IMetaDataDispenserEx::FindAssemblyModule (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 365bea0bdd32fa1b408ba0bfdf100cc443b5d419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446230"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="0822f-102">IMetaDataDispenserEx::FindAssemblyModule (Método)</span><span class="sxs-lookup"><span data-stu-id="0822f-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="0822f-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="0822f-103">This method is not implemented.</span></span> <span data-ttu-id="0822f-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="0822f-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0822f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0822f-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0822f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0822f-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="0822f-107">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="0822f-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="0822f-108">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="0822f-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="0822f-109">[in] No usado.</span><span class="sxs-lookup"><span data-stu-id="0822f-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="0822f-110">[in] El nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="0822f-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="0822f-111">[in] El ensamblado va a calcular.</span><span class="sxs-lookup"><span data-stu-id="0822f-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="0822f-112">[out] El nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="0822f-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0822f-113">[in] El tamaño, en bytes, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="0822f-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="0822f-114">[out] El número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="0822f-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0822f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0822f-115">Requirements</span></span>  
 <span data-ttu-id="0822f-116">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0822f-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0822f-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0822f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0822f-118">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0822f-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0822f-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0822f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0822f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0822f-120">See Also</span></span>  
 [<span data-ttu-id="0822f-121">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0822f-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="0822f-122">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0822f-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
