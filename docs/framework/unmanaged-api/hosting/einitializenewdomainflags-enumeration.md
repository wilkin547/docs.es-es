---
description: 'Más información sobre: enumeración Einitializenewdomainflags ('
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
ms.openlocfilehash: b856d061e86c0c79b35f842975378307b79a37e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785470"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="0ddad-103">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0ddad-103">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="0ddad-104">Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ddad-104">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ddad-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0ddad-106">Members</span><span class="sxs-lookup"><span data-stu-id="0ddad-106">Members</span></span>  
  
|<span data-ttu-id="0ddad-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="0ddad-107">Member</span></span>|<span data-ttu-id="0ddad-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ddad-108">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="0ddad-109">Sin marcas.</span><span class="sxs-lookup"><span data-stu-id="0ddad-109">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="0ddad-110">Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el <xref:System.AppDomainManager.InitializeNewDomain%2A> método.</span><span class="sxs-lookup"><span data-stu-id="0ddad-110">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ddad-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ddad-111">Remarks</span></span>  

 <span data-ttu-id="0ddad-112">El método [ICLRDomainManager:: setappdomainmanagertype (](iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="0ddad-112">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddad-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ddad-113">Requirements</span></span>  

 <span data-ttu-id="0ddad-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddad-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddad-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0ddad-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ddad-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ddad-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddad-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddad-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddad-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ddad-118">See also</span></span>

- [<span data-ttu-id="0ddad-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="0ddad-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="0ddad-120">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="0ddad-120">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
