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
ms.openlocfilehash: 84b2c0571a7991829e65b45759bd61fa4009aa71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445882"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="943ab-102">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="943ab-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="943ab-103">Establece o cambia las características de firma de PInvoke de un método, tal como se define mediante una llamada anterior a [IMetaDataEmit:: DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="943ab-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="943ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="943ab-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="943ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="943ab-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="943ab-106">[in] El `mdToken` para la asignación de qué información se aplica.</span><span class="sxs-lookup"><span data-stu-id="943ab-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="943ab-107">[in] Marcadores utilizados por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="943ab-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="943ab-108">Se trata de una máscara de bits de `CorPinvokeMap` valores.</span><span class="sxs-lookup"><span data-stu-id="943ab-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="943ab-109">[in] El nombre de la exportación de destino en la DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="943ab-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="943ab-110">[in] El `mdModuleRef` token para el destino de DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="943ab-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="943ab-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="943ab-111">Requirements</span></span>  
 <span data-ttu-id="943ab-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943ab-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="943ab-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="943ab-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="943ab-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="943ab-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="943ab-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943ab-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="943ab-116">See Also</span></span>  
 [<span data-ttu-id="943ab-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="943ab-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="943ab-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="943ab-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
