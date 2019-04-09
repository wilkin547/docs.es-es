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
ms.openlocfilehash: 7e5fb3ab1d2dedb220fd4a486409512414233021
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176675"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="e43f6-102">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e43f6-102">EClrUnhandledException Enumeration</span></span>
<span data-ttu-id="e43f6-103">Describe las opciones disponibles para administrar las excepciones que no se controlan en código de usuario.</span><span class="sxs-lookup"><span data-stu-id="e43f6-103">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e43f6-104">Syntax</span></span>  
  
```  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="e43f6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e43f6-105">Members</span></span>  
  
|<span data-ttu-id="e43f6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e43f6-106">Member</span></span>|<span data-ttu-id="e43f6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e43f6-107">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="e43f6-108">Especifica que se produce el comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e43f6-108">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="e43f6-109">El proceso se cierra.</span><span class="sxs-lookup"><span data-stu-id="e43f6-109">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="e43f6-110">Especifica que common language runtime (CLR) pasa por alto las excepciones no controladas y permite al host determinar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e43f6-110">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e43f6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e43f6-111">Remarks</span></span>  
 <span data-ttu-id="e43f6-112">Para especificar que el CLR se comportan como las versiones anteriores, use el `eHostDeterminedPolicy` miembro.</span><span class="sxs-lookup"><span data-stu-id="e43f6-112">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e43f6-113">Requirements</span></span>  
 <span data-ttu-id="e43f6-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43f6-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e43f6-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e43f6-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e43f6-116">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e43f6-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e43f6-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e43f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e43f6-118">See also</span></span>

- [<span data-ttu-id="e43f6-119">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e43f6-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="e43f6-120">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e43f6-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="e43f6-121">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e43f6-121">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e43f6-122">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="e43f6-122">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="e43f6-123">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e43f6-123">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="e43f6-124">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="e43f6-124">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
