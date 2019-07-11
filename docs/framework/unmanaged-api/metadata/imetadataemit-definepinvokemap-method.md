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
ms.openlocfilehash: c6421ca47c3439d94c1ae86caaf2198298872d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777519"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="0f70d-102">IMetaDataEmit::DefinePinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="0f70d-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="0f70d-103">Establece las características de la firma PInvoke del método al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="0f70d-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f70d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f70d-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f70d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f70d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0f70d-106">[in] El token para el método de destino.</span><span class="sxs-lookup"><span data-stu-id="0f70d-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="0f70d-107">[in] Marcas usadas por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="0f70d-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="0f70d-108">[in] El nombre del destino de exportación de método en una DLL no administrada.</span><span class="sxs-lookup"><span data-stu-id="0f70d-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="0f70d-109">[in] El token para el destino de archivo DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="0f70d-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f70d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f70d-110">Requirements</span></span>  
 <span data-ttu-id="0f70d-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f70d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f70d-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f70d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f70d-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0f70d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f70d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f70d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f70d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f70d-115">See also</span></span>

- [<span data-ttu-id="0f70d-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f70d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0f70d-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f70d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
