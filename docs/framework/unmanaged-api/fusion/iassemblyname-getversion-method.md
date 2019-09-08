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
ms.openlocfilehash: 58919936bdc62d52437f429146f04c66d49294b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796582"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="f7fbb-102">IAssemblyName::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="f7fbb-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="f7fbb-103">Obtiene la información de versión para el ensamblado al que hace referencia este objeto de [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f7fbb-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7fbb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7fbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7fbb-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="f7fbb-106">enuncia Los bits 32 altos de la versión.</span><span class="sxs-lookup"><span data-stu-id="f7fbb-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="f7fbb-107">enuncia Los bits 32 bajos de la versión.</span><span class="sxs-lookup"><span data-stu-id="f7fbb-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7fbb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7fbb-108">Requirements</span></span>  
 <span data-ttu-id="f7fbb-109">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7fbb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7fbb-110">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f7fbb-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f7fbb-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7fbb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7fbb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7fbb-112">See also</span></span>

- [<span data-ttu-id="f7fbb-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7fbb-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
