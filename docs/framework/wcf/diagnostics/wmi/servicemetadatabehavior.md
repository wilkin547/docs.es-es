---
title: ServiceMetadataBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c05f6be9fc0507b7e2f1de4374e3b9bbe3e2a10e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="b0791-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b0791-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="b0791-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="b0791-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0791-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0791-104">Syntax</span></span>  
  
```  
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b0791-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0791-105">Methods</span></span>  
 <span data-ttu-id="b0791-106">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b0791-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b0791-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b0791-107">Properties</span></span>  
 <span data-ttu-id="b0791-108">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0791-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="b0791-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="b0791-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="b0791-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0791-110">Data type: string</span></span>  
  
 <span data-ttu-id="b0791-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0791-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0791-112">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="b0791-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="b0791-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b0791-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="b0791-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b0791-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b0791-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0791-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0791-116">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="b0791-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="b0791-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="b0791-117">HttpGetUrl</span></span>  
 <span data-ttu-id="b0791-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0791-118">Data type: string</span></span>  
  
 <span data-ttu-id="b0791-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0791-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0791-120">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="b0791-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="b0791-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="b0791-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="b0791-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b0791-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b0791-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0791-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0791-124">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="b0791-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="b0791-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="b0791-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="b0791-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="b0791-126">Data type: string</span></span>  
  
 <span data-ttu-id="b0791-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b0791-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b0791-128">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b0791-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0791-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0791-129">Requirements</span></span>  
  
|<span data-ttu-id="b0791-130">MOF</span><span class="sxs-lookup"><span data-stu-id="b0791-130">MOF</span></span>|<span data-ttu-id="b0791-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b0791-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b0791-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b0791-132">Namespace</span></span>|<span data-ttu-id="b0791-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b0791-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0791-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0791-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
