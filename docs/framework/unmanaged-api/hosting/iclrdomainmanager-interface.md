---
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
ms.openlocfilehash: dda243ccbf18f396c1bcc03358997ea0f06c42a8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615714"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="7f57b-102">ICLRDomainManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f57b-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="7f57b-103">Permite al host especificar el administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado y para especificar las propiedades de inicialización.</span><span class="sxs-lookup"><span data-stu-id="7f57b-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f57b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7f57b-104">Methods</span></span>  
  
|<span data-ttu-id="7f57b-105">Método</span><span class="sxs-lookup"><span data-stu-id="7f57b-105">Method</span></span>|<span data-ttu-id="7f57b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f57b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f57b-107">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="7f57b-107">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="7f57b-108">Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f57b-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="7f57b-109">Método SetPropertiesForDefaultAppDomain</span><span class="sxs-lookup"><span data-stu-id="7f57b-109">SetPropertiesForDefaultAppDomain Method</span></span>](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="7f57b-110">Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7f57b-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f57b-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7f57b-111">Remarks</span></span>  
 <span data-ttu-id="7f57b-112">Para obtener una instancia de esta interfaz, llame al método [ICLRControl:: GetCLRManager (](iclrcontrol-getclrmanager-method.md) con el IID de tipo de administrador `IID_ICLRDomainManager` .</span><span class="sxs-lookup"><span data-stu-id="7f57b-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f57b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f57b-113">Requirements</span></span>  
 <span data-ttu-id="7f57b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f57b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f57b-115">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="7f57b-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7f57b-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7f57b-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f57b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f57b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f57b-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="7f57b-118">See also</span></span>

- [<span data-ttu-id="7f57b-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="7f57b-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="7f57b-120">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="7f57b-120">Hosting</span></span>](index.md)
