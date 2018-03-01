---
title: "IAssemblyName::GetProperty (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3311cc79cd010f59d707283fa555a2ebf66e53db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="0376f-102">IAssemblyName::GetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="0376f-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="0376f-103">Obtiene un puntero a la propiedad al que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="0376f-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0376f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0376f-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0376f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0376f-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="0376f-106">[in] El identificador único para la propiedad solicitada.</span><span class="sxs-lookup"><span data-stu-id="0376f-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="0376f-107">[out] Los datos de propiedades que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="0376f-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="0376f-108">[entrada, salida] El tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="0376f-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0376f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0376f-109">Requirements</span></span>  
 <span data-ttu-id="0376f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0376f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0376f-111">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0376f-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0376f-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0376f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0376f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0376f-113">See Also</span></span>  
 [<span data-ttu-id="0376f-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0376f-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
