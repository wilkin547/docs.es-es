---
title: EContextType (Enumeración)
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: c6d1ace12bd07fa1f14c8570eca1f950a5c22be9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686337"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="bfe27-102">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bfe27-102">EContextType Enumeration</span></span>

<span data-ttu-id="bfe27-103">Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="bfe27-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfe27-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="bfe27-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="bfe27-105">Members</span></span>  
  
|<span data-ttu-id="bfe27-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="bfe27-106">Member</span></span>|<span data-ttu-id="bfe27-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfe27-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="bfe27-108">Indica el contexto del subproceso actual en el momento en que el Common Language Runtime (CLR) llama al método [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) o el contexto solicitado por CLR en una llamada al método [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bfe27-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="bfe27-109">Indica un contexto sobre el que el host tiene privilegios más bajos, como el recolector de elementos no utilizados, o los constructores de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="bfe27-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfe27-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfe27-110">Remarks</span></span>  

 <span data-ttu-id="bfe27-111">CLR proporciona uno de los `EContextType` valores como un valor de parámetro en las llamadas a `IHostSecurityManager::GetSecurityContext` los `IHostSecurityManager::SetSecurityContext` métodos y.</span><span class="sxs-lookup"><span data-stu-id="bfe27-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfe27-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bfe27-112">Requirements</span></span>  

 <span data-ttu-id="bfe27-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfe27-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfe27-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bfe27-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfe27-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfe27-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfe27-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfe27-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe27-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bfe27-117">See also</span></span>

- [<span data-ttu-id="bfe27-118">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfe27-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="bfe27-119">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bfe27-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="bfe27-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="bfe27-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
