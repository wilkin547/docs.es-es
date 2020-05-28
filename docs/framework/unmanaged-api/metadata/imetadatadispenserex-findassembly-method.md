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
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006199"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="a10d8-102">IMetaDataDispenserEx::FindAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="a10d8-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="a10d8-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="a10d8-103">This method is not implemented.</span></span> <span data-ttu-id="a10d8-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="a10d8-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a10d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a10d8-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a10d8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a10d8-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="a10d8-107">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a10d8-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="a10d8-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a10d8-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="a10d8-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="a10d8-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="a10d8-110">de Ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a10d8-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="a10d8-111">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a10d8-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a10d8-112">de Tamaño, en bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="a10d8-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="a10d8-113">enuncia Número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="a10d8-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a10d8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a10d8-114">Requirements</span></span>  
 <span data-ttu-id="a10d8-115">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a10d8-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a10d8-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a10d8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a10d8-117">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a10d8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a10d8-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a10d8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a10d8-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a10d8-119">See also</span></span>

- [<span data-ttu-id="a10d8-120">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a10d8-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="a10d8-121">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a10d8-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
