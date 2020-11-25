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
ms.openlocfilehash: c11a4498610c3e82590a0ff9be1247173e70be76
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713397"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="46369-102">IMetaDataDispenserEx::FindAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="46369-102">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="46369-103">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="46369-103">This method is not implemented.</span></span> <span data-ttu-id="46369-104">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="46369-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46369-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46369-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="46369-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46369-106">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="46369-107">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="46369-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="46369-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="46369-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="46369-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="46369-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="46369-110">de Ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="46369-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="46369-111">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="46369-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="46369-112">de Tamaño, en bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="46369-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="46369-113">enuncia Número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="46369-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46369-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46369-114">Requirements</span></span>  

 <span data-ttu-id="46369-115">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46369-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46369-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="46369-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46369-117">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46369-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46369-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46369-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46369-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46369-119">See also</span></span>

- [<span data-ttu-id="46369-120">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46369-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="46369-121">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46369-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
