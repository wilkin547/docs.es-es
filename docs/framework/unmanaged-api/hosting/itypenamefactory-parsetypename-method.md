---
title: ITypeNameFactory::ParseTypeName (Método)
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
ms.openlocfilehash: 493c5136587eec8f1da85d15a2e7f3ecd235bcd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123318"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="335d0-102">ITypeNameFactory::ParseTypeName (Método)</span><span class="sxs-lookup"><span data-stu-id="335d0-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="335d0-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="335d0-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="335d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="335d0-104">Syntax</span></span>  
  
```cpp  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="335d0-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="335d0-105">Requirements</span></span>  
 <span data-ttu-id="335d0-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="335d0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="335d0-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="335d0-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="335d0-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="335d0-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="335d0-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="335d0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="335d0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="335d0-110">See also</span></span>

- [<span data-ttu-id="335d0-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="335d0-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
