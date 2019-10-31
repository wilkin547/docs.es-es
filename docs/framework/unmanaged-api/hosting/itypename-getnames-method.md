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
ms.openlocfilehash: 66934db3f1507262ffb2e9eec232f21574c29348
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095754"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="7e4a7-102">ITypeName::GetNames (Método)</span><span class="sxs-lookup"><span data-stu-id="7e4a7-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="7e4a7-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="7e4a7-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e4a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7e4a7-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e4a7-105">Requirements</span></span>  
 <span data-ttu-id="7e4a7-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e4a7-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e4a7-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7e4a7-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e4a7-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7e4a7-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e4a7-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e4a7-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4a7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e4a7-110">See also</span></span>

- [<span data-ttu-id="7e4a7-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7e4a7-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
