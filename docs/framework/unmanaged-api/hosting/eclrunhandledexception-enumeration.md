---
title: EClrUnhandledException (Enumeración)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65910745aa6291f93fd42d8f99a0e84dc1e38fdd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686691"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="a4a1e-102">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="a4a1e-103">Describe las opciones disponibles para administrar las excepciones que no se controlan en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4a1e-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="a4a1e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a4a1e-105">Members</span></span>  
  
|<span data-ttu-id="a4a1e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a4a1e-106">Member</span></span>|<span data-ttu-id="a4a1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4a1e-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="a4a1e-108">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="a4a1e-109">El proceso se cierra.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="a4a1e-110">Especifica que common language runtime (CLR) pasa por alto las excepciones no controladas y permite al host determinar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a1e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4a1e-111">Remarks</span></span>  
 <span data-ttu-id="a4a1e-112">Para especificar que el CLR se comportan como las versiones anteriores, use el `eHostDeterminedPolicy` miembro.</span><span class="sxs-lookup"><span data-stu-id="a4a1e-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4a1e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4a1e-113">Requirements</span></span>  
 <span data-ttu-id="a4a1e-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4a1e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a1e-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4a1e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4a1e-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4a1e-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4a1e-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a1e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a1e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4a1e-118">See also</span></span>
- [<span data-ttu-id="a4a1e-119">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="a4a1e-120">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="a4a1e-121">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="a4a1e-122">SetUnhandledExceptionPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="a4a1e-123">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a4a1e-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="a4a1e-124">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="a4a1e-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
