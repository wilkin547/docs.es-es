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
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731727"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="e6f9a-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="e6f9a-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="e6f9a-103">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6f9a-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="e6f9a-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="e6f9a-105">Interfaces</span></span>  
  
|<span data-ttu-id="e6f9a-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="e6f9a-106">Interface</span></span>|<span data-ttu-id="e6f9a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6f9a-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="e6f9a-108">Proporciona métodos para crear, inicializar y administrar un proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6f9a-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6f9a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6f9a-109">Requirements</span></span>  

 <span data-ttu-id="e6f9a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f9a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f9a-111">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="e6f9a-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e6f9a-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6f9a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f9a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f9a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f9a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6f9a-114">See also</span></span>

- [<span data-ttu-id="e6f9a-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="e6f9a-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
