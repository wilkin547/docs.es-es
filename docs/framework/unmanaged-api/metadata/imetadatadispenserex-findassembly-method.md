---
description: 'Más información sobre: IMetaDataDispenserEx:: Findassembly ((método)'
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
ms.openlocfilehash: 6bed016e9235281b42f5a3231ef2aff284b6cc3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753606"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="d44b6-103">IMetaDataDispenserEx::FindAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="d44b6-103">IMetaDataDispenserEx::FindAssembly Method</span></span>

<span data-ttu-id="d44b6-104">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="d44b6-104">This method is not implemented.</span></span> <span data-ttu-id="d44b6-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d44b6-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44b6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d44b6-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d44b6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d44b6-107">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="d44b6-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d44b6-108">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="d44b6-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d44b6-109">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="d44b6-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d44b6-110">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="d44b6-111">de Ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="d44b6-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="d44b6-112">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d44b6-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d44b6-113">de Tamaño, en bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="d44b6-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="d44b6-114">enuncia Número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="d44b6-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d44b6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d44b6-115">Requirements</span></span>  

 <span data-ttu-id="d44b6-116">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d44b6-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d44b6-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d44b6-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d44b6-118">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d44b6-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d44b6-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d44b6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44b6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d44b6-120">See also</span></span>

- [<span data-ttu-id="d44b6-121">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d44b6-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d44b6-122">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d44b6-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
