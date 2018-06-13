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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a261d9164e8714531eab1fe9fc8148304e6d5bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432887"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="3f43e-102">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3f43e-102">EContextType Enumeration</span></span>
<span data-ttu-id="3f43e-103">Describe el contexto de seguridad del subproceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="3f43e-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f43e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f43e-104">Syntax</span></span>  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="3f43e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3f43e-105">Members</span></span>  
  
|<span data-ttu-id="3f43e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3f43e-106">Member</span></span>|<span data-ttu-id="3f43e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f43e-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="3f43e-108">Indica el contexto en el subproceso actual en el momento en que common language runtime (CLR) llama el [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) método o el contexto solicitado por CLR en una llamada a la [ IHostSecurityManager:: SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="3f43e-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="3f43e-109">Indica un contexto sobre el que el host tiene menos privilegios, como el recolector de elementos no utilizados o los constructores de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="3f43e-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f43e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3f43e-110">Remarks</span></span>  
 <span data-ttu-id="3f43e-111">El CLR proporciona uno de los `EContextType` valores como valor de parámetro en las llamadas a la `IHostSecurityManager::GetSecurityContext` y `IHostSecurityManager::SetSecurityContext` métodos.</span><span class="sxs-lookup"><span data-stu-id="3f43e-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f43e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f43e-112">Requirements</span></span>  
 <span data-ttu-id="3f43e-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f43e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f43e-114">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f43e-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f43e-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3f43e-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f43e-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f43e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f43e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f43e-117">See Also</span></span>  
 [<span data-ttu-id="3f43e-118">IHostSecurityContext (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f43e-118">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="3f43e-119">IHostSecurityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3f43e-119">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="3f43e-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="3f43e-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
