---
description: 'Más información sobre: enumeración Econtexttype ('
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
ms.openlocfilehash: b7d6ddb385386bb0616a01ef6fcc432f2c925d51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785541"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="13fb3-103">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="13fb3-103">EContextType Enumeration</span></span>

<span data-ttu-id="13fb3-104">Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="13fb3-104">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fb3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13fb3-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="13fb3-106">Members</span><span class="sxs-lookup"><span data-stu-id="13fb3-106">Members</span></span>  
  
|<span data-ttu-id="13fb3-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="13fb3-107">Member</span></span>|<span data-ttu-id="13fb3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="13fb3-108">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="13fb3-109">Indica el contexto del subproceso actual en el momento en que el Common Language Runtime (CLR) llama al método [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) o el contexto solicitado por CLR en una llamada al método [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="13fb3-109">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="13fb3-110">Indica un contexto sobre el que el host tiene privilegios más bajos, como el recolector de elementos no utilizados, o los constructores de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="13fb3-110">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13fb3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="13fb3-111">Remarks</span></span>  

 <span data-ttu-id="13fb3-112">CLR proporciona uno de los `EContextType` valores como un valor de parámetro en las llamadas a `IHostSecurityManager::GetSecurityContext` los `IHostSecurityManager::SetSecurityContext` métodos y.</span><span class="sxs-lookup"><span data-stu-id="13fb3-112">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fb3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13fb3-113">Requirements</span></span>  

 <span data-ttu-id="13fb3-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13fb3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fb3-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="13fb3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13fb3-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13fb3-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13fb3-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fb3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fb3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="13fb3-118">See also</span></span>

- [<span data-ttu-id="13fb3-119">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13fb3-119">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="13fb3-120">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13fb3-120">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="13fb3-121">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="13fb3-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
