---
description: 'Más información acerca de: coclase Comcallunmarshal ('
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
ms.openlocfilehash: 508c1183e2862a286e9db0390bc0348629a9db8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799842"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="a8064-103">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="a8064-103">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="a8064-104">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="a8064-104">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8064-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8064-105">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="a8064-106">Interfaces</span><span class="sxs-lookup"><span data-stu-id="a8064-106">Interfaces</span></span>  
  
|<span data-ttu-id="a8064-107">Interfaz</span><span class="sxs-lookup"><span data-stu-id="a8064-107">Interface</span></span>|<span data-ttu-id="a8064-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8064-108">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="a8064-109">Proporciona métodos para crear, inicializar y administrar un proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="a8064-109">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8064-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8064-110">Requirements</span></span>  

 <span data-ttu-id="a8064-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8064-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8064-112">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="a8064-112">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="a8064-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8064-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8064-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8064-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8064-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8064-115">See also</span></span>

- [<span data-ttu-id="a8064-116">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="a8064-116">Hosting Coclasses</span></span>](hosting-coclasses.md)
