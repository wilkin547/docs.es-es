---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196822"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="9f284-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="9f284-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="9f284-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="9f284-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f284-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f284-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9f284-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9f284-105">Methods</span></span>  
 <span data-ttu-id="9f284-106">La clase ServiceAuthorizationBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="9f284-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9f284-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9f284-107">Properties</span></span>  
 <span data-ttu-id="9f284-108">La clase ServiceAuthorizationBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f284-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="9f284-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="9f284-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="9f284-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="9f284-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="9f284-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f284-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f284-112">Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="9f284-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="9f284-113">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="9f284-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="9f284-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f284-114">Data type: string</span></span>  
  
 <span data-ttu-id="9f284-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f284-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f284-116">El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9f284-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="9f284-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="9f284-117">RoleProvider</span></span>  
 <span data-ttu-id="9f284-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f284-118">Data type: string</span></span>  
  
 <span data-ttu-id="9f284-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f284-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f284-120">Nombre del proveedor de funciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9f284-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="9f284-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="9f284-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="9f284-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f284-122">Data type: string</span></span>  
  
 <span data-ttu-id="9f284-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9f284-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f284-124">El administrador de autorización utilizado para la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="9f284-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f284-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f284-125">Requirements</span></span>  
  
|<span data-ttu-id="9f284-126">MOF</span><span class="sxs-lookup"><span data-stu-id="9f284-126">MOF</span></span>|<span data-ttu-id="9f284-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9f284-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9f284-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9f284-128">Namespace</span></span>|<span data-ttu-id="9f284-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9f284-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f284-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f284-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
