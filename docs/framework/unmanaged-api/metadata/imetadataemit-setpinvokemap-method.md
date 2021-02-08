---
description: 'Más información sobre: IMetaDataEmit:: Setpinvokemap ((método)'
title: IMetaDataEmit::SetPinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: e50f06385b599a99454da0a9b971b00806d3140a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771852"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="2c109-103">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="2c109-103">IMetaDataEmit::SetPinvokeMap Method</span></span>

<span data-ttu-id="2c109-104">Establece o cambia las características de la firma PInvoke de un método, tal como se define en una llamada anterior a [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="2c109-104">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c109-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c109-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c109-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c109-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="2c109-107">de `mdToken` Al que se aplica la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="2c109-107">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="2c109-108">de Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="2c109-108">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="2c109-109">Se trata de una máscara de máscara de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="2c109-109">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="2c109-110">de Nombre de la exportación de destino en el archivo DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="2c109-110">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="2c109-111">de El `mdModuleRef` token para el archivo dll de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="2c109-111">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c109-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c109-112">Requirements</span></span>  

 <span data-ttu-id="2c109-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c109-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c109-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2c109-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c109-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c109-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c109-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c109-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c109-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c109-117">See also</span></span>

- [<span data-ttu-id="2c109-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c109-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2c109-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c109-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
