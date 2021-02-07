---
description: 'Más información sobre: IMetaDataDispenserEx:: Findassemblymodule ((método)'
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
ms.openlocfilehash: 39ea13a2d8f2436e86db513aaa33f990f43d8132
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753580"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="d9c38-103">IMetaDataDispenserEx::FindAssemblyModule (Método)</span><span class="sxs-lookup"><span data-stu-id="d9c38-103">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>

<span data-ttu-id="d9c38-104">Este método no se implementa.</span><span class="sxs-lookup"><span data-stu-id="d9c38-104">This method is not implemented.</span></span> <span data-ttu-id="d9c38-105">Si se llama, devuelve E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="d9c38-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c38-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9c38-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d9c38-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9c38-107">Parameters</span></span>  

 `szAppBase`  
 <span data-ttu-id="d9c38-108">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d9c38-108">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="d9c38-109">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d9c38-109">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="d9c38-110">[in] No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d9c38-110">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="d9c38-111">de Nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="d9c38-111">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="d9c38-112">de Ensamblado que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="d9c38-112">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="d9c38-113">enuncia Nombre simple del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d9c38-113">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d9c38-114">de Tamaño, en bytes, de `szName` .</span><span class="sxs-lookup"><span data-stu-id="d9c38-114">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="d9c38-115">enuncia Número de caracteres devueltos realmente en `szName` .</span><span class="sxs-lookup"><span data-stu-id="d9c38-115">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9c38-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9c38-116">Requirements</span></span>  

 <span data-ttu-id="d9c38-117">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9c38-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9c38-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d9c38-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9c38-119">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9c38-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9c38-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9c38-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c38-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9c38-121">See also</span></span>

- [<span data-ttu-id="d9c38-122">IMetaDataDispenserEx (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9c38-122">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d9c38-123">IMetaDataDispenser (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9c38-123">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
