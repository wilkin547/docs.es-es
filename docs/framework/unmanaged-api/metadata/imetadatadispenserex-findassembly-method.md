---
title: IMetaDataDispenserEx::FindAssembly (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3fc0d59bfb8a5b5c41955b52ae3f2ea99fbc46e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502441"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="1e627-102">IMetaDataDispenserEx::FindAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="1e627-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="1e627-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="1e627-103">This method is not implemented.</span></span> <span data-ttu-id="1e627-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1e627-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e627-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e627-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1e627-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e627-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="1e627-107">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="1e627-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="1e627-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="1e627-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="1e627-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="1e627-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="1e627-110">[in] El ensamblado que se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="1e627-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="1e627-111">[out] El nombre sencillo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1e627-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1e627-112">[in] El tamaño, en bytes, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="1e627-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="1e627-113">[out] El número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="1e627-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e627-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e627-114">Requirements</span></span>  
 <span data-ttu-id="1e627-115">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e627-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e627-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1e627-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e627-117">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e627-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e627-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e627-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e627-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e627-119">See also</span></span>
- [<span data-ttu-id="1e627-120">IMetaDataDispenserEx (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e627-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1e627-121">IMetaDataDispenser (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e627-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
