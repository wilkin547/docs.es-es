---
title: IAssemblyName::GetVersion (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a28cb9f1fd2e12cd750d4eeb8db6c2d7a181b414
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197430"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="f9d00-102">IAssemblyName::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="f9d00-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="f9d00-103">Obtiene la información de versión del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="f9d00-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9d00-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9d00-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9d00-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="f9d00-106">[out] 32 bits superiores de la versión.</span><span class="sxs-lookup"><span data-stu-id="f9d00-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="f9d00-107">[out] 32 bits inferiores de la versión.</span><span class="sxs-lookup"><span data-stu-id="f9d00-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9d00-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f9d00-108">Requirements</span></span>  
 <span data-ttu-id="f9d00-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9d00-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9d00-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f9d00-110">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="f9d00-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f9d00-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9d00-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9d00-112">See also</span></span>

- [<span data-ttu-id="f9d00-113">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9d00-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
