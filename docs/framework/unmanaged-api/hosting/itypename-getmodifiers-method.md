---
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
ms.openlocfilehash: 64751032c017473ffd82248b310b14c087f74129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727840"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="b2d01-102">ITypeName::GetModifiers (Método)</span><span class="sxs-lookup"><span data-stu-id="b2d01-102">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="b2d01-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b2d01-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2d01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b2d01-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2d01-105">Requirements</span></span>  

 <span data-ttu-id="b2d01-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2d01-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2d01-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2d01-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2d01-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2d01-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2d01-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2d01-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d01-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b2d01-110">See also</span></span>

- [<span data-ttu-id="b2d01-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b2d01-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
