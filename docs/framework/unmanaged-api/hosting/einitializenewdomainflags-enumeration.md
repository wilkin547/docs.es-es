---
title: EInitializeNewDomainFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d69b12404459de5dbc1c7748deee6ca09c1e5182
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772412"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="e2083-102">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e2083-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="e2083-103">Permite que el host proporcionar el tiempo de ejecución con información sobre la inicialización de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2083-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2083-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2083-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e2083-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e2083-105">Members</span></span>  
  
|<span data-ttu-id="e2083-106">Member</span><span class="sxs-lookup"><span data-stu-id="e2083-106">Member</span></span>|<span data-ttu-id="e2083-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e2083-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="e2083-108">Ninguna marca.</span><span class="sxs-lookup"><span data-stu-id="e2083-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="e2083-109">Informa a common language runtime (CLR) que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el <xref:System.AppDomainManager.InitializeNewDomain%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e2083-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2083-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2083-110">Remarks</span></span>  
 <span data-ttu-id="e2083-111">El [ICLRDomainManager](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) método toma un parámetro de tipo `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="e2083-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2083-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2083-112">Requirements</span></span>  
 <span data-ttu-id="e2083-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2083-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2083-114">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2083-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2083-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2083-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2083-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2083-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2083-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2083-117">See also</span></span>

- [<span data-ttu-id="e2083-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="e2083-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="e2083-119">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="e2083-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
