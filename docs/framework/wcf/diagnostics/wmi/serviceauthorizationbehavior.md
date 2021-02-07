---
description: 'Más información acerca de: ServiceAuthorizationBehavior'
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: dc398621103774a04934aa23ae3d7208f4389717
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715592"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="87500-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="87500-103">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="87500-104">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="87500-104">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87500-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87500-105">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87500-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="87500-106">Methods</span></span>  

 <span data-ttu-id="87500-107">La clase ServiceAuthorizationBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="87500-107">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87500-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87500-108">Properties</span></span>  

 <span data-ttu-id="87500-109">La clase ServiceAuthorizationBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="87500-109">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="87500-110">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="87500-110">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="87500-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="87500-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="87500-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87500-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87500-113">Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="87500-113">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="87500-114">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="87500-114">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="87500-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="87500-115">Data type: string</span></span>  
  
 <span data-ttu-id="87500-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87500-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87500-117">El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="87500-117">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="87500-118">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="87500-118">RoleProvider</span></span>  

 <span data-ttu-id="87500-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="87500-119">Data type: string</span></span>  
  
 <span data-ttu-id="87500-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87500-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87500-121">Nombre del proveedor de funciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="87500-121">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="87500-122">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="87500-122">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="87500-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="87500-123">Data type: string</span></span>  
  
 <span data-ttu-id="87500-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="87500-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87500-125">El administrador de autorización utilizado para la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="87500-125">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87500-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87500-126">Requirements</span></span>  
  
|<span data-ttu-id="87500-127">MOF</span><span class="sxs-lookup"><span data-stu-id="87500-127">MOF</span></span>|<span data-ttu-id="87500-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="87500-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87500-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="87500-129">Namespace</span></span>|<span data-ttu-id="87500-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87500-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87500-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="87500-131">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
