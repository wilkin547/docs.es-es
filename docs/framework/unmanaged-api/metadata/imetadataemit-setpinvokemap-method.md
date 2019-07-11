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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a6fd0a9ae798fa5071d9b4b9fac1f8b3c759a20
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750874"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="1a397-102">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="1a397-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="1a397-103">Establece o cambia las características de una firma de método PInvoke, tal como se define mediante una llamada anterior a [DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="1a397-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a397-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a397-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a397-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a397-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1a397-106">[in] El `mdToken` a que la asignación se aplica la información.</span><span class="sxs-lookup"><span data-stu-id="1a397-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="1a397-107">[in] Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="1a397-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="1a397-108">Se trata de una máscara de bits de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="1a397-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="1a397-109">[in] El nombre del destino de exportación en la DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="1a397-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="1a397-110">[in] El `mdModuleRef` token para el destino de DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="1a397-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a397-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a397-111">Requirements</span></span>  
 <span data-ttu-id="1a397-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a397-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a397-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a397-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a397-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1a397-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a397-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a397-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a397-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a397-116">See also</span></span>

- [<span data-ttu-id="1a397-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a397-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1a397-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a397-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
