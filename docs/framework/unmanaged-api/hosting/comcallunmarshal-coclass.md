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
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166886"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="495ba-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="495ba-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="495ba-103">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="495ba-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="495ba-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="495ba-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="495ba-105">Interfaces</span></span>  
  
|<span data-ttu-id="495ba-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="495ba-106">Interface</span></span>|<span data-ttu-id="495ba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="495ba-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="495ba-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="495ba-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="495ba-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="495ba-109">Requirements</span></span>  
 <span data-ttu-id="495ba-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="495ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="495ba-111">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="495ba-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="495ba-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="495ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="495ba-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="495ba-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="495ba-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="495ba-114">See also</span></span>

- [<span data-ttu-id="495ba-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="495ba-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
