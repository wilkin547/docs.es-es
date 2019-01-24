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
ms.openlocfilehash: ca2d7fe73fc749296f76e18ecce75b7fdd0795d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585596"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="ce8fc-102">IAssemblyName::SetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="ce8fc-102">IAssemblyName::SetProperty Method</span></span>
<span data-ttu-id="ce8fc-103">Establece el valor de la propiedad al que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="ce8fc-103">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce8fc-104">Syntax</span></span>  
  
```  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce8fc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce8fc-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="ce8fc-106">[in] El identificador único de la propiedad cuyo valor se establecerá.</span><span class="sxs-lookup"><span data-stu-id="ce8fc-106">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="ce8fc-107">[in] El valor que se va a establecer la propiedad al que hace referencia `PropertyId`.</span><span class="sxs-lookup"><span data-stu-id="ce8fc-107">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="ce8fc-108">[in] El tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="ce8fc-108">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce8fc-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce8fc-109">Requirements</span></span>  
 <span data-ttu-id="ce8fc-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce8fc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce8fc-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ce8fc-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ce8fc-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce8fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce8fc-113">See also</span></span>
- [<span data-ttu-id="ce8fc-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce8fc-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
