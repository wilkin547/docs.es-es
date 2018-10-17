---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374305"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="b66bc-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b66bc-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="b66bc-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b66bc-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b66bc-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b66bc-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b66bc-105">Methods</span></span>  
 <span data-ttu-id="b66bc-106">La clase ServiceAuthorizationBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b66bc-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b66bc-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b66bc-107">Properties</span></span>  
 <span data-ttu-id="b66bc-108">La clase ServiceAuthorizationBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b66bc-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="b66bc-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="b66bc-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="b66bc-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b66bc-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b66bc-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b66bc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b66bc-112">Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="b66bc-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="b66bc-113">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="b66bc-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="b66bc-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b66bc-114">Data type: string</span></span>  
  
 <span data-ttu-id="b66bc-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b66bc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b66bc-116">El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b66bc-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="b66bc-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="b66bc-117">RoleProvider</span></span>  
 <span data-ttu-id="b66bc-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b66bc-118">Data type: string</span></span>  
  
 <span data-ttu-id="b66bc-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b66bc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b66bc-120">Nombre del proveedor de funciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b66bc-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="b66bc-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="b66bc-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="b66bc-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b66bc-122">Data type: string</span></span>  
  
 <span data-ttu-id="b66bc-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b66bc-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b66bc-124">El administrador de autorización utilizado para la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="b66bc-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b66bc-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b66bc-125">Requirements</span></span>  
  
|<span data-ttu-id="b66bc-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b66bc-126">MOF</span></span>|<span data-ttu-id="b66bc-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b66bc-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b66bc-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b66bc-128">Namespace</span></span>|<span data-ttu-id="b66bc-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b66bc-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b66bc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b66bc-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
