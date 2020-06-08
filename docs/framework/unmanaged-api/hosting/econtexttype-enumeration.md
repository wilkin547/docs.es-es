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
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493427"
---
# <a name="econtexttype-enumeration"></a><span data-ttu-id="444c3-102">EContextType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="444c3-102">EContextType Enumeration</span></span>
<span data-ttu-id="444c3-103">Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="444c3-103">Describes the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="444c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="444c3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a><span data-ttu-id="444c3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="444c3-105">Members</span></span>  
  
|<span data-ttu-id="444c3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="444c3-106">Member</span></span>|<span data-ttu-id="444c3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="444c3-107">Description</span></span>|  
|------------|-----------------|  
|`eCurrentContext`|<span data-ttu-id="444c3-108">Indica el contexto del subproceso actual en el momento en que el Common Language Runtime (CLR) llama al método [IHostSecurityManager:: GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) o el contexto solicitado por CLR en una llamada al método [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="444c3-108">Indicates the context on the current thread at the time the common language runtime (CLR) calls the [IHostSecurityManager::GetSecurityContext](ihostsecuritymanager-getsecuritycontext-method.md) method, or the context requested by the CLR in a call to the [IHostSecurityManager::SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) method.</span></span>|  
|`eRestrictedContext`|<span data-ttu-id="444c3-109">Indica un contexto sobre el que el host tiene privilegios más bajos, como el recolector de elementos no utilizados, o los constructores de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="444c3-109">Indicates a context over which the host has lower privileges, such as the garbage collector, or class or module constructors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="444c3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="444c3-110">Remarks</span></span>  
 <span data-ttu-id="444c3-111">CLR proporciona uno de los `EContextType` valores como un valor de parámetro en las llamadas a `IHostSecurityManager::GetSecurityContext` los `IHostSecurityManager::SetSecurityContext` métodos y.</span><span class="sxs-lookup"><span data-stu-id="444c3-111">The CLR supplies one of the `EContextType` values as a parameter value in calls to the `IHostSecurityManager::GetSecurityContext` and `IHostSecurityManager::SetSecurityContext` methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="444c3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="444c3-112">Requirements</span></span>  
 <span data-ttu-id="444c3-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="444c3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="444c3-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="444c3-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="444c3-115">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="444c3-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="444c3-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="444c3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="444c3-117">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="444c3-117">See also</span></span>

- [<span data-ttu-id="444c3-118">IHostSecurityContext (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="444c3-118">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="444c3-119">IHostSecurityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="444c3-119">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="444c3-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="444c3-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
