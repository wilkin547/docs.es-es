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
ms.openlocfilehash: 302db0d029b3811d151473323a7a60bd16a00ec1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131235"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="affb3-102">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="affb3-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="affb3-103">Describe las opciones disponibles para administrar excepciones que no se controlan en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="affb3-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="affb3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="affb3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="affb3-105">Members</span></span>  
  
|<span data-ttu-id="affb3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="affb3-106">Member</span></span>|<span data-ttu-id="affb3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="affb3-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="affb3-108">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="affb3-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="affb3-109">El proceso se ha anulado.</span><span class="sxs-lookup"><span data-stu-id="affb3-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="affb3-110">Especifica que el Common Language Runtime (CLR) omite las excepciones no controladas y permite que el host determine cualquier acción más.</span><span class="sxs-lookup"><span data-stu-id="affb3-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="affb3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="affb3-111">Remarks</span></span>  
 <span data-ttu-id="affb3-112">Para especificar que el CLR se comporte como versiones anteriores, utilice el miembro `eHostDeterminedPolicy`.</span><span class="sxs-lookup"><span data-stu-id="affb3-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="affb3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="affb3-113">Requirements</span></span>  
 <span data-ttu-id="affb3-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="affb3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="affb3-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="affb3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="affb3-116">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="affb3-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="affb3-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="affb3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="affb3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="affb3-118">See also</span></span>

- [<span data-ttu-id="affb3-119">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="affb3-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="affb3-120">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="affb3-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="affb3-121">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="affb3-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="affb3-122">SetUnhandledExceptionPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="affb3-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="affb3-123">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="affb3-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="affb3-124">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="affb3-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
