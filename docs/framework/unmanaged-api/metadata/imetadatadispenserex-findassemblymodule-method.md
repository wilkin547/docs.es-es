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
ms.openlocfilehash: 2d1d97e443be884f45187a2811ddfce106249515
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183136"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="870ad-102">IMetaDataDispenserEx::FindAssemblyModule (Método)</span><span class="sxs-lookup"><span data-stu-id="870ad-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="870ad-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="870ad-103">This method is not implemented.</span></span> <span data-ttu-id="870ad-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="870ad-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="870ad-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="870ad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="870ad-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="870ad-107">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="870ad-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="870ad-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="870ad-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="870ad-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="870ad-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="870ad-110">[in] El nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="870ad-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="870ad-111">[in] El ensamblado que se va a calcular.</span><span class="sxs-lookup"><span data-stu-id="870ad-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="870ad-112">[out] El nombre sencillo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="870ad-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="870ad-113">[in] El tamaño, en bytes, de `szName`.</span><span class="sxs-lookup"><span data-stu-id="870ad-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="870ad-114">[out] El número de caracteres devueltos realmente en `szName`.</span><span class="sxs-lookup"><span data-stu-id="870ad-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870ad-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="870ad-115">Requirements</span></span>  
 <span data-ttu-id="870ad-116">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="870ad-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="870ad-117">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="870ad-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="870ad-118">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="870ad-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="870ad-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="870ad-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="870ad-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="870ad-120">See also</span></span>

- [<span data-ttu-id="870ad-121">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="870ad-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="870ad-122">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="870ad-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
