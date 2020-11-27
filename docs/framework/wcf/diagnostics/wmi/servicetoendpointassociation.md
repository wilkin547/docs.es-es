---
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 6e20556541b1aa48e7dfc6a8cde97e1bc477457e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273950"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="56ee9-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="56ee9-102">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="56ee9-103">Asigna un servicio a un extremo.</span><span class="sxs-lookup"><span data-stu-id="56ee9-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56ee9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56ee9-104">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="56ee9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="56ee9-105">Methods</span></span>  

 <span data-ttu-id="56ee9-106">La clase ServiceToEndpointAssociation no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="56ee9-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="56ee9-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="56ee9-107">Properties</span></span>  

 <span data-ttu-id="56ee9-108">La clase ServiceToEndpointAssociation tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="56ee9-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="56ee9-109">ref</span><span class="sxs-lookup"><span data-stu-id="56ee9-109">ref</span></span>  

 <span data-ttu-id="56ee9-110">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="56ee9-110">Data type: Service</span></span>  
  
 <span data-ttu-id="56ee9-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56ee9-111">Access type: Read-only</span></span>  
<span data-ttu-id="56ee9-112">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="56ee9-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="56ee9-113">El servicio asociado con el extremo.</span><span class="sxs-lookup"><span data-stu-id="56ee9-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="56ee9-114">ref</span><span class="sxs-lookup"><span data-stu-id="56ee9-114">ref</span></span>  

 <span data-ttu-id="56ee9-115">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="56ee9-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="56ee9-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="56ee9-116">Access type: Read-only</span></span>  
<span data-ttu-id="56ee9-117">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="56ee9-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="56ee9-118">El punto de conexión asociado con el servicio.</span><span class="sxs-lookup"><span data-stu-id="56ee9-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56ee9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56ee9-119">Requirements</span></span>  
  
|<span data-ttu-id="56ee9-120">MOF</span><span class="sxs-lookup"><span data-stu-id="56ee9-120">MOF</span></span>|<span data-ttu-id="56ee9-121">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="56ee9-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="56ee9-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="56ee9-122">Namespace</span></span>|<span data-ttu-id="56ee9-123">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="56ee9-123">Defined in root\ServiceModel</span></span>|
