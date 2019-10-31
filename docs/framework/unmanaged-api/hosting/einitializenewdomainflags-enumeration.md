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
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129413"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="61404-102">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="61404-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="61404-103">Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="61404-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61404-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61404-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="61404-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="61404-105">Members</span></span>  
  
|<span data-ttu-id="61404-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="61404-106">Member</span></span>|<span data-ttu-id="61404-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="61404-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="61404-108">Sin marcas.</span><span class="sxs-lookup"><span data-stu-id="61404-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="61404-109">Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el método <xref:System.AppDomainManager.InitializeNewDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="61404-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61404-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="61404-110">Remarks</span></span>  
 <span data-ttu-id="61404-111">El método [ICLRDomainManager:: setappdomainmanagertype (](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags`.</span><span class="sxs-lookup"><span data-stu-id="61404-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61404-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61404-112">Requirements</span></span>  
 <span data-ttu-id="61404-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61404-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61404-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="61404-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61404-115">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="61404-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61404-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61404-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61404-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="61404-117">See also</span></span>

- [<span data-ttu-id="61404-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="61404-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="61404-119">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="61404-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
