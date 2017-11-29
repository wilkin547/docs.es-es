---
title: ServiceToEndpointAssociation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03c3cd15-e1b2-4dc2-bdc2-59fdccdae110
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d2755294ba02b4d67bd7f62cf020a44525874d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="servicetoendpointassociation"></a><span data-ttu-id="ac429-102">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="ac429-102">ServiceToEndpointAssociation</span></span>
<span data-ttu-id="ac429-103">Asigna un servicio a un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ac429-103">Maps a service to an endpoint.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac429-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac429-104">Syntax</span></span>  
  
```  
class ServiceToEndpointAssociation  
{  
  Service ref;  
  Endpoint ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ac429-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ac429-105">Methods</span></span>  
 <span data-ttu-id="ac429-106">La clase ServiceToEndpointAssociation no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="ac429-106">The ServiceToEndpointAssociation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ac429-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ac429-107">Properties</span></span>  
 <span data-ttu-id="ac429-108">La clase ServiceToEndpointAssociation tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="ac429-108">The ServiceToEndpointAssociation class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ac429-109">ref</span><span class="sxs-lookup"><span data-stu-id="ac429-109">ref</span></span>  
 <span data-ttu-id="ac429-110">Tipo de datos: servicio</span><span class="sxs-lookup"><span data-stu-id="ac429-110">Data type: Service</span></span>  
  
 <span data-ttu-id="ac429-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ac429-111">Access type: Read-only</span></span>  
<span data-ttu-id="ac429-112">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="ac429-112">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ac429-113">El servicio asociado con el extremo.</span><span class="sxs-lookup"><span data-stu-id="ac429-113">The service associated with the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ac429-114">ref</span><span class="sxs-lookup"><span data-stu-id="ac429-114">ref</span></span>  
 <span data-ttu-id="ac429-115">Tipo de datos: extremo</span><span class="sxs-lookup"><span data-stu-id="ac429-115">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="ac429-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="ac429-116">Access type: Read-only</span></span>  
<span data-ttu-id="ac429-117">Calificadores: clave</span><span class="sxs-lookup"><span data-stu-id="ac429-117">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="ac429-118">El extremo asociado con el servicio.</span><span class="sxs-lookup"><span data-stu-id="ac429-118">The endpoint associated with the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac429-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac429-119">Requirements</span></span>  
  
|<span data-ttu-id="ac429-120">MOF</span><span class="sxs-lookup"><span data-stu-id="ac429-120">MOF</span></span>|<span data-ttu-id="ac429-121">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="ac429-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ac429-122">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ac429-122">Namespace</span></span>|<span data-ttu-id="ac429-123">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ac429-123">Defined in root\ServiceModel</span></span>|
