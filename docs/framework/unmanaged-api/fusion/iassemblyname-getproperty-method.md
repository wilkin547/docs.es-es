---
title: IAssemblyName::GetProperty (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c297c2476cb35fef861cda77f4f6f536fd85557
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428196"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="c9748-102">IAssemblyName::GetProperty (Método)</span><span class="sxs-lookup"><span data-stu-id="c9748-102">IAssemblyName::GetProperty Method</span></span>
<span data-ttu-id="c9748-103">Obtiene un puntero a la propiedad al que hace referencia el identificador de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="c9748-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9748-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9748-104">Syntax</span></span>  
  
```  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9748-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9748-105">Parameters</span></span>  
 `PropertyId`  
 <span data-ttu-id="c9748-106">[in] El identificador único para la propiedad solicitada.</span><span class="sxs-lookup"><span data-stu-id="c9748-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="c9748-107">[out] Los datos de propiedades que se devuelven.</span><span class="sxs-lookup"><span data-stu-id="c9748-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="c9748-108">[entrada, salida] El tamaño, en bytes, de `pvProperty`.</span><span class="sxs-lookup"><span data-stu-id="c9748-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9748-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9748-109">Requirements</span></span>  
 <span data-ttu-id="c9748-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9748-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9748-111">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c9748-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c9748-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9748-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9748-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9748-113">See Also</span></span>  
 [<span data-ttu-id="c9748-114">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9748-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
