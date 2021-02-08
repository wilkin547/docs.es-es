---
description: 'Más información acerca de: interfaz ICLRDomainManager'
title: ICLRDomainManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: d719e89d81e8c7abb1f238ce50b4e236de17ac72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790014"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="d4738-103">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4738-103">ICLRDomainManager Interface</span></span>

<span data-ttu-id="d4738-104">Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="d4738-104">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d4738-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4738-105">Methods</span></span>  
  
|<span data-ttu-id="d4738-106">Método</span><span class="sxs-lookup"><span data-stu-id="d4738-106">Method</span></span>|<span data-ttu-id="d4738-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4738-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d4738-108">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="d4738-108">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="d4738-109">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d4738-109">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="d4738-110">Método SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="d4738-110">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="d4738-111">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d4738-111">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4738-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4738-112">Remarks</span></span>  

 <span data-ttu-id="d4738-113">Para obtener una instancia de esta interfaz, llame al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) con el IID de tipo de administrador `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="d4738-113">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4738-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4738-114">Requirements</span></span>  

 <span data-ttu-id="d4738-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4738-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4738-116">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d4738-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d4738-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4738-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4738-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4738-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4738-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4738-119">See also</span></span>

- [<span data-ttu-id="d4738-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d4738-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d4738-121">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d4738-121">Hosting</span></span>](index.md)
