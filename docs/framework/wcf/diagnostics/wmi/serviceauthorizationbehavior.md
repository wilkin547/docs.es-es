---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273209"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="06780-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="06780-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="06780-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="06780-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06780-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06780-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="06780-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="06780-105">Methods</span></span>  

 <span data-ttu-id="06780-106">La clase ServiceAuthorizationBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="06780-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="06780-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="06780-107">Properties</span></span>  

 <span data-ttu-id="06780-108">La clase ServiceAuthorizationBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="06780-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="06780-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="06780-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="06780-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="06780-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="06780-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="06780-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06780-112">Un valor que controla si el servicio intenta suplantar mediante las credenciales proporcionadas por el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="06780-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="06780-113">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="06780-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="06780-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="06780-114">Data type: string</span></span>  
  
 <span data-ttu-id="06780-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="06780-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06780-116">El nombre de entidad de seguridad usado para llevar a cabo las operaciones en el servidor.</span><span class="sxs-lookup"><span data-stu-id="06780-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="06780-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="06780-117">RoleProvider</span></span>  

 <span data-ttu-id="06780-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="06780-118">Data type: string</span></span>  
  
 <span data-ttu-id="06780-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="06780-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06780-120">Nombre del proveedor de funciones de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="06780-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="06780-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="06780-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="06780-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="06780-122">Data type: string</span></span>  
  
 <span data-ttu-id="06780-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="06780-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="06780-124">El administrador de autorización utilizado para la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="06780-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06780-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06780-125">Requirements</span></span>  
  
|<span data-ttu-id="06780-126">MOF</span><span class="sxs-lookup"><span data-stu-id="06780-126">MOF</span></span>|<span data-ttu-id="06780-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="06780-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="06780-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="06780-128">Namespace</span></span>|<span data-ttu-id="06780-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="06780-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06780-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="06780-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
