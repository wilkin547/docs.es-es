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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616234"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="ff8a8-102">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ff8a8-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="ff8a8-103">Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff8a8-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff8a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff8a8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ff8a8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ff8a8-105">Members</span></span>  
  
|<span data-ttu-id="ff8a8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ff8a8-106">Member</span></span>|<span data-ttu-id="ff8a8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff8a8-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="ff8a8-108">Sin marcas.</span><span class="sxs-lookup"><span data-stu-id="ff8a8-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="ff8a8-109">Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el <xref:System.AppDomainManager.InitializeNewDomain%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ff8a8-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff8a8-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff8a8-110">Remarks</span></span>  
 <span data-ttu-id="ff8a8-111">El método [ICLRDomainManager:: setappdomainmanagertype (](iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="ff8a8-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff8a8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff8a8-112">Requirements</span></span>  
 <span data-ttu-id="ff8a8-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff8a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff8a8-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ff8a8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff8a8-115">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ff8a8-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff8a8-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff8a8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff8a8-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ff8a8-117">See also</span></span>

- [<span data-ttu-id="ff8a8-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="ff8a8-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="ff8a8-119">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="ff8a8-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
