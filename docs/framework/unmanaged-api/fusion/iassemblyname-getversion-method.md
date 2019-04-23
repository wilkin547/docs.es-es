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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197430"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="045eb-102">IAssemblyName::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="045eb-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="045eb-103">Obtiene la información de versión del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="045eb-103">Gets the version information for the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="045eb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="045eb-104">Syntax</span></span>  
  
```  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="045eb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="045eb-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="045eb-106">[out] 32 bits superiores de la versión.</span><span class="sxs-lookup"><span data-stu-id="045eb-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="045eb-107">[out] 32 bits inferiores de la versión.</span><span class="sxs-lookup"><span data-stu-id="045eb-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="045eb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="045eb-108">Requirements</span></span>  
 <span data-ttu-id="045eb-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="045eb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="045eb-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="045eb-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="045eb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="045eb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="045eb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="045eb-112">See also</span></span>

- [<span data-ttu-id="045eb-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="045eb-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
