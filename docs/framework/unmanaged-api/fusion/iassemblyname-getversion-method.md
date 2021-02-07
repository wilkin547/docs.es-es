---
description: 'Más información sobre: IAssemblyName:: GetVersion (método)'
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
ms.openlocfilehash: 3339dda6a0b4f083655ece7bef86b080a8fcf5c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760724"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="1d2da-103">IAssemblyName::GetVersion (Método)</span><span class="sxs-lookup"><span data-stu-id="1d2da-103">IAssemblyName::GetVersion Method</span></span>

<span data-ttu-id="1d2da-104">Obtiene la información de versión para el ensamblado al que hace referencia este objeto de [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1d2da-104">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d2da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d2da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d2da-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d2da-106">Parameters</span></span>  

 `pdwVersionHi`  
 <span data-ttu-id="1d2da-107">enuncia Los bits 32 altos de la versión.</span><span class="sxs-lookup"><span data-stu-id="1d2da-107">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="1d2da-108">enuncia Los bits 32 bajos de la versión.</span><span class="sxs-lookup"><span data-stu-id="1d2da-108">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d2da-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d2da-109">Requirements</span></span>  

 <span data-ttu-id="1d2da-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d2da-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d2da-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1d2da-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1d2da-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d2da-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d2da-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d2da-113">See also</span></span>

- [<span data-ttu-id="1d2da-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d2da-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
