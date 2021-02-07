---
description: 'Más información acerca de: ServiceToEndpointAssociation'
title: ServiceToEndpointAssociation
ms.date: 03/30/2017
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
ms.openlocfilehash: 1ae2ce2bcc0b3494b00fffa750f3ca46d26fe08f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715345"
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="116cf-103">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="116cf-103">ServiceToEndpointAssociation</span></span>

<span data-ttu-id="116cf-104">Asigna un servicio a un extremo.</span><span class="sxs-lookup"><span data-stu-id="116cf-104">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="116cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="116cf-105">Syntax</span></span>  
  
```csharp
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="116cf-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="116cf-106">Methods</span></span>  

 <span data-ttu-id="116cf-107">La clase ServiceToEndpointAssociation no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="116cf-107">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="116cf-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="116cf-108">Properties</span></span>  

 <span data-ttu-id="116cf-109">La clase ServiceToEndpointAssociation tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="116cf-109">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="116cf-110">ref</span><span class="sxs-lookup"><span data-stu-id="116cf-110">ref</span></span>  

 <span data-ttu-id="116cf-111">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="116cf-111">Data type: Service</span></span>  
  
 <span data-ttu-id="116cf-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="116cf-112">Access type: Read-only</span></span>  
<span data-ttu-id="116cf-113">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="116cf-113">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="116cf-114">El servicio asociado con el extremo.</span><span class="sxs-lookup"><span data-stu-id="116cf-114">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="116cf-115">ref</span><span class="sxs-lookup"><span data-stu-id="116cf-115">ref</span></span>  

 <span data-ttu-id="116cf-116">Tipo de datos: punto de conexión</span><span class="sxs-lookup"><span data-stu-id="116cf-116">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="116cf-117">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="116cf-117">Access type: Read-only</span></span>  
<span data-ttu-id="116cf-118">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="116cf-118">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="116cf-119">El punto de conexión asociado con el servicio.</span><span class="sxs-lookup"><span data-stu-id="116cf-119">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="116cf-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="116cf-120">Requirements</span></span>  
  
|<span data-ttu-id="116cf-121">MOF</span><span class="sxs-lookup"><span data-stu-id="116cf-121">MOF</span></span>|<span data-ttu-id="116cf-122">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="116cf-122">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="116cf-123">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="116cf-123">Namespace</span></span>|<span data-ttu-id="116cf-124">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="116cf-124">Defined in root\ServiceModel</span></span>|
