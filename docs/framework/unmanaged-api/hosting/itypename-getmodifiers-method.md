---
description: 'Más información sobre: ITypeName:: GetModifiers (método)'
title: ITypeName::GetModifiers (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 3c44d569255656f95ccceec0462d09044b46679b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753723"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="f0401-103">ITypeName::GetModifiers (Método)</span><span class="sxs-lookup"><span data-stu-id="f0401-103">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="f0401-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="f0401-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0401-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0401-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f0401-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0401-106">Requirements</span></span>  

 <span data-ttu-id="f0401-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0401-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0401-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f0401-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0401-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0401-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0401-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0401-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0401-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0401-111">See also</span></span>

- [<span data-ttu-id="f0401-112">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f0401-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
