---
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
ms.openlocfilehash: 236fc848087f64c2327c2c9e790065cc3f64dc58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704310"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="5a092-102">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="5a092-102">IMetaDataEmit::SetPinvokeMap Method</span></span>

<span data-ttu-id="5a092-103">Establece o cambia las características de la firma PInvoke de un método, tal como se define en una llamada anterior a [IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a092-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a092-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a092-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a092-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a092-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="5a092-106">de `mdToken` Al que se aplica la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="5a092-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="5a092-107">de Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="5a092-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="5a092-108">Se trata de una máscara de máscara de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="5a092-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="5a092-109">de Nombre de la exportación de destino en el archivo DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="5a092-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="5a092-110">de El `mdModuleRef` token para el archivo dll de destino no administrado.</span><span class="sxs-lookup"><span data-stu-id="5a092-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a092-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a092-111">Requirements</span></span>  

 <span data-ttu-id="5a092-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a092-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a092-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a092-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a092-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a092-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a092-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a092-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a092-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a092-116">See also</span></span>

- [<span data-ttu-id="5a092-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a092-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5a092-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a092-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
