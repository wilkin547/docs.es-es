---
title: ITypeName::GetNames (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
ms.openlocfilehash: 91e73f8e3d2e3c372d3fe1c4fd4fccf6ff67b363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727814"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="c2cbd-102">ITypeName::GetNames (Método)</span><span class="sxs-lookup"><span data-stu-id="c2cbd-102">ITypeName::GetNames Method</span></span>

<span data-ttu-id="c2cbd-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="c2cbd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2cbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2cbd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c2cbd-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2cbd-105">Requirements</span></span>  

 <span data-ttu-id="c2cbd-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2cbd-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2cbd-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c2cbd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2cbd-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2cbd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2cbd-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2cbd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2cbd-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2cbd-110">See also</span></span>

- [<span data-ttu-id="c2cbd-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c2cbd-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
