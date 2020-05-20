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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616741"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="856c6-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="856c6-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="856c6-103">Proporciona interfaces para administrar el cálculo de referencias de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="856c6-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="856c6-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="856c6-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="856c6-105">Interfaces</span></span>  
  
|<span data-ttu-id="856c6-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="856c6-106">Interface</span></span>|<span data-ttu-id="856c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="856c6-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="856c6-108">Proporciona métodos para crear, inicializar y administrar un proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="856c6-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="856c6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="856c6-109">Requirements</span></span>  
 <span data-ttu-id="856c6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856c6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856c6-111">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="856c6-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="856c6-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="856c6-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="856c6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="856c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856c6-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="856c6-114">See also</span></span>

- [<span data-ttu-id="856c6-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="856c6-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
