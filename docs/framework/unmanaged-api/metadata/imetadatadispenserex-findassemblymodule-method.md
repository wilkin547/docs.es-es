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
ms.openlocfilehash: 64f1e2a8f05616c7ca84bc130428629b1176e985
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006186"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="abf99-102">IMetaDataDispenserEx::FindAssemblyModule (Método)</span><span class="sxs-lookup"><span data-stu-id="abf99-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="abf99-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="abf99-103">This method is not implemented.</span></span> <span data-ttu-id="abf99-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="abf99-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abf99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abf99-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="abf99-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abf99-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="abf99-107">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="abf99-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="abf99-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="abf99-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="abf99-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="abf99-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="abf99-110">de Nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="abf99-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="abf99-111">de Ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="abf99-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="abf99-112">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abf99-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="abf99-113">de Tamaño, en bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="abf99-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="abf99-114">enuncia Número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="abf99-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abf99-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abf99-115">Requirements</span></span>  
 <span data-ttu-id="abf99-116">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abf99-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abf99-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="abf99-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abf99-118">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="abf99-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="abf99-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abf99-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abf99-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abf99-120">See also</span></span>

- [<span data-ttu-id="abf99-121">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abf99-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="abf99-122">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abf99-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
