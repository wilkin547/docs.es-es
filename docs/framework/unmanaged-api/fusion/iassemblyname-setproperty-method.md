---
title: IAssemblyName::SetProperty (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbb04a97597982fdae7a68ba4f3ed4d7420b4189
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488154"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="f1cbc-102">IAssemblyName::SetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="f1cbc-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="f1cbc-103">Establece el valor de la propiedad al que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="f1cbc-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cbc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1cbc-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1cbc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1cbc-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="f1cbc-106">[in] El identificador único de la propiedad cuyo valor se establecerá.</span><span class="sxs-lookup"><span data-stu-id="f1cbc-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="f1cbc-107">[in] El valor que se va a establecer la propiedad al que hace referencia `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="f1cbc-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="f1cbc-108">[in] El tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="f1cbc-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1cbc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1cbc-109">Requirements</span></span>  
 <span data-ttu-id="f1cbc-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1cbc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1cbc-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f1cbc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f1cbc-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1cbc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cbc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1cbc-113">See also</span></span>
- [<span data-ttu-id="f1cbc-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1cbc-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
