---
title: ComCallUnmarshal (Coclase)
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779083"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="5a654-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="5a654-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="5a654-103">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5a654-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a654-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a654-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5a654-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="5a654-105">Interfaces</span></span>  
  
|<span data-ttu-id="5a654-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="5a654-106">Interface</span></span>|<span data-ttu-id="5a654-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5a654-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="5a654-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="5a654-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a654-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a654-109">Requirements</span></span>  
 <span data-ttu-id="5a654-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a654-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a654-111">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5a654-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5a654-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a654-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a654-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a654-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a654-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a654-114">See also</span></span>

- [<span data-ttu-id="5a654-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="5a654-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
