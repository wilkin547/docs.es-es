---
title: ComCallUnmarshal (Coclase)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ComCallUnmarshal Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: ComCallUnmarshal
helpviewer_keywords: ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cbaefd2b2c3b79a97107f4aaa394a3db2c68b33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="635d4-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="635d4-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="635d4-103">Proporciona interfaces para administrar la serialización de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="635d4-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635d4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="635d4-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="635d4-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="635d4-105">Interfaces</span></span>  
  
|<span data-ttu-id="635d4-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="635d4-106">Interface</span></span>|<span data-ttu-id="635d4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="635d4-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="635d4-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="635d4-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="635d4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="635d4-109">Requirements</span></span>  
 <span data-ttu-id="635d4-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="635d4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635d4-111">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="635d4-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="635d4-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="635d4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="635d4-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635d4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635d4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="635d4-114">See Also</span></span>  
 [<span data-ttu-id="635d4-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="635d4-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
