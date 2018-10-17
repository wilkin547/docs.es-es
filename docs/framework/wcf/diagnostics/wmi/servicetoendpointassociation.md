---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 3d23a3ee10c47e04ea7bdba202ea5063c0d84fac
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49372192"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="6133d-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="6133d-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="6133d-103">Asigna un servicio a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6133d-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6133d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6133d-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6133d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6133d-105">Methods</span></span>  
 <span data-ttu-id="6133d-106">La clase ServiceToEndpointAssociation no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="6133d-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6133d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6133d-107">Properties</span></span>  
 <span data-ttu-id="6133d-108">La clase ServiceToEndpointAssociation tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="6133d-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6133d-109">ref</span><span class="sxs-lookup"><span data-stu-id="6133d-109">ref</span></span>  
 <span data-ttu-id="6133d-110">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="6133d-110">Data type: Service</span></span>  
  
 <span data-ttu-id="6133d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6133d-111">Access type: Read-only</span></span>  
<span data-ttu-id="6133d-112">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="6133d-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6133d-113">El servicio asociado con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6133d-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="6133d-114">ref</span><span class="sxs-lookup"><span data-stu-id="6133d-114">ref</span></span>  
 <span data-ttu-id="6133d-115">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="6133d-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="6133d-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="6133d-116">Access type: Read-only</span></span>  
<span data-ttu-id="6133d-117">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="6133d-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="6133d-118">El punto de conexión asociado con el servicio.</span><span class="sxs-lookup"><span data-stu-id="6133d-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6133d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6133d-119">Requirements</span></span>  
  
|<span data-ttu-id="6133d-120">MOF</span><span class="sxs-lookup"><span data-stu-id="6133d-120">MOF</span></span>|<span data-ttu-id="6133d-121">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="6133d-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6133d-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6133d-122">Namespace</span></span>|<span data-ttu-id="6133d-123">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6133d-123">Defined in root\ServiceModel</span></span>|
