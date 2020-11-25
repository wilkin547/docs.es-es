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
ms.openlocfilehash: 8350b507609e63c060cda08514200d386c37a6b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724330"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="48d05-102">EInitializeNewDomainFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="48d05-102">EInitializeNewDomainFlags Enumeration</span></span>

<span data-ttu-id="48d05-103">Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="48d05-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d05-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="48d05-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="48d05-105">Members</span></span>  
  
|<span data-ttu-id="48d05-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="48d05-106">Member</span></span>|<span data-ttu-id="48d05-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="48d05-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="48d05-108">Sin marcas.</span><span class="sxs-lookup"><span data-stu-id="48d05-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="48d05-109">Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el <xref:System.AppDomainManager.InitializeNewDomain%2A> método.</span><span class="sxs-lookup"><span data-stu-id="48d05-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48d05-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48d05-110">Remarks</span></span>  

 <span data-ttu-id="48d05-111">El método [ICLRDomainManager:: setappdomainmanagertype (](iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags` .</span><span class="sxs-lookup"><span data-stu-id="48d05-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d05-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d05-112">Requirements</span></span>  

 <span data-ttu-id="48d05-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d05-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d05-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48d05-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48d05-115">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48d05-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48d05-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d05-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d05-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48d05-117">See also</span></span>

- [<span data-ttu-id="48d05-118">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="48d05-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="48d05-119">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="48d05-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
