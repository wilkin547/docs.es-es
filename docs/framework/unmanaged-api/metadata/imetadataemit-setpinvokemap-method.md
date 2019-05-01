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
ms.openlocfilehash: b838a83a160707e546b05ef334eb17d0c6e6cc27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050004"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="c20a3-102">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="c20a3-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="c20a3-103">Establece o cambia las características de una firma de método PInvoke, tal como se define mediante una llamada anterior a [DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="c20a3-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c20a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c20a3-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c20a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c20a3-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c20a3-106">[in] El `mdToken` a que la asignación se aplica la información.</span><span class="sxs-lookup"><span data-stu-id="c20a3-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="c20a3-107">[in] Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="c20a3-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="c20a3-108">Se trata de una máscara de bits de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="c20a3-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="c20a3-109">[in] El nombre del destino de exportación en la DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="c20a3-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="c20a3-110">[in] El `mdModuleRef` token para el destino de DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="c20a3-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c20a3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c20a3-111">Requirements</span></span>  
 <span data-ttu-id="c20a3-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c20a3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c20a3-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c20a3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c20a3-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c20a3-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c20a3-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c20a3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c20a3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c20a3-116">See also</span></span>

- [<span data-ttu-id="c20a3-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c20a3-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c20a3-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c20a3-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
