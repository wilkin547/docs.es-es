---
title: IMetaDataEmit::DefinePinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 480fedc8ae63ffa3222a74e39297cc64b6812e97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444496"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="3998a-102">IMetaDataEmit::DefinePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="3998a-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="3998a-103">Establece las características de la firma PInvoke del método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="3998a-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3998a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3998a-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3998a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3998a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="3998a-106">[in] El token para el método de destino.</span><span class="sxs-lookup"><span data-stu-id="3998a-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="3998a-107">[in] Marcadores utilizados por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="3998a-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="3998a-108">[in] El nombre del destino de la exportación de método en una DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="3998a-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="3998a-109">[in] El token para el destino de archivo DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="3998a-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3998a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3998a-110">Requirements</span></span>  
 <span data-ttu-id="3998a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3998a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3998a-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3998a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3998a-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3998a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3998a-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3998a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3998a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3998a-115">See Also</span></span>  
 [<span data-ttu-id="3998a-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3998a-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="3998a-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3998a-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
