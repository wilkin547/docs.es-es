---
title: "EClrUnhandledException (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8fcc9254499724d94153c445943fdaf78d12a10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="ac281-102">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac281-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="ac281-103">Describe las opciones disponibles para administrar las excepciones que son no está controladas en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac281-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac281-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac281-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="ac281-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ac281-105">Members</span></span>  
  
|<span data-ttu-id="ac281-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ac281-106">Member</span></span>|<span data-ttu-id="ac281-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac281-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="ac281-108">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ac281-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="ac281-109">El proceso se cierra.</span><span class="sxs-lookup"><span data-stu-id="ac281-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="ac281-110">Especifica que common language runtime (CLR) omite las excepciones no controladas y permite que el host determine las acciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="ac281-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac281-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac281-111">Remarks</span></span>  
 <span data-ttu-id="ac281-112">Para especificar que CLR se comporte como en versiones anteriores, use el `eHostDeterminedPolicy` miembro.</span><span class="sxs-lookup"><span data-stu-id="ac281-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac281-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac281-113">Requirements</span></span>  
 <span data-ttu-id="ac281-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac281-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac281-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac281-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac281-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac281-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac281-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac281-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac281-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac281-118">See Also</span></span>  
 [<span data-ttu-id="ac281-119">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac281-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="ac281-120">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac281-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="ac281-121">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac281-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="ac281-122">SetUnhandledExceptionPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="ac281-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)  
 [<span data-ttu-id="ac281-123">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac281-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="ac281-124">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="ac281-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
