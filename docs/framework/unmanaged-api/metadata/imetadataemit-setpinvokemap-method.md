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
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175595"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="cfd6f-102">IMetaDataEmit::SetPinvokeMap (Método)</span><span class="sxs-lookup"><span data-stu-id="cfd6f-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="cfd6f-103">Establece o cambia las características de la firma PInvoke de un método, tal como se define mediante una llamada anterior a [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="cfd6f-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfd6f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfd6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cfd6f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="cfd6f-106">[en] El `mdToken` a qué se aplica la información de asignación.</span><span class="sxs-lookup"><span data-stu-id="cfd6f-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="cfd6f-107">[en] Indicadores utilizados por PInvoke para realizar la asignación.</span><span class="sxs-lookup"><span data-stu-id="cfd6f-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="cfd6f-108">Esta es una `CorPinvokeMap` máscara de bits de valores.</span><span class="sxs-lookup"><span data-stu-id="cfd6f-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="cfd6f-109">[en] El nombre de la exportación de destino en el archivo DLL nativo.</span><span class="sxs-lookup"><span data-stu-id="cfd6f-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="cfd6f-110">[en] El `mdModuleRef` token para el archivo DLL no administrado de destino.</span><span class="sxs-lookup"><span data-stu-id="cfd6f-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfd6f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfd6f-111">Requirements</span></span>  
 <span data-ttu-id="cfd6f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfd6f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfd6f-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cfd6f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cfd6f-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cfd6f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cfd6f-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfd6f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfd6f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cfd6f-116">See also</span></span>

- [<span data-ttu-id="cfd6f-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfd6f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="cfd6f-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cfd6f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
