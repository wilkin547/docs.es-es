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
ms.openlocfilehash: 7884d53630ca13a30d7b4efd55d46684a9dd7d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427647"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="2229f-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="2229f-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="2229f-103">Proporciona interfaces para administrar la serialización de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="2229f-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2229f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2229f-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2229f-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="2229f-105">Interfaces</span></span>  
  
|<span data-ttu-id="2229f-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="2229f-106">Interface</span></span>|<span data-ttu-id="2229f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2229f-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="2229f-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="2229f-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2229f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2229f-109">Requirements</span></span>  
 <span data-ttu-id="2229f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2229f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2229f-111">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2229f-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2229f-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2229f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2229f-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2229f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2229f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="2229f-114">See Also</span></span>  
 [<span data-ttu-id="2229f-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="2229f-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
