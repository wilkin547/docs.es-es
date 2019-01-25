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
ms.openlocfilehash: 5a404448c45a37d50794ceae9a9bf8ff6af08eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574578"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="cb989-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="cb989-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="cb989-103">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="cb989-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb989-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb989-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="cb989-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="cb989-105">Interfaces</span></span>  
  
|<span data-ttu-id="cb989-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="cb989-106">Interface</span></span>|<span data-ttu-id="cb989-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb989-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="cb989-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="cb989-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb989-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb989-109">Requirements</span></span>  
 <span data-ttu-id="cb989-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb989-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb989-111">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="cb989-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="cb989-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb989-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb989-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb989-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb989-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb989-114">See also</span></span>
- [<span data-ttu-id="cb989-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="cb989-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
