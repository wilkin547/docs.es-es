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
ms.openlocfilehash: f17b31e1dfe9ba60b2042a85a6d673d986fe0a33
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="9c53e-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="9c53e-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="9c53e-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="9c53e-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c53e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c53e-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9c53e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9c53e-105">Methods</span></span>  
 <span data-ttu-id="9c53e-106">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="9c53e-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9c53e-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9c53e-107">Properties</span></span>  
 <span data-ttu-id="9c53e-108">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c53e-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="9c53e-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="9c53e-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="9c53e-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9c53e-110">Data type: string</span></span>  
  
 <span data-ttu-id="9c53e-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c53e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c53e-112">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="9c53e-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="9c53e-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9c53e-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="9c53e-114">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="9c53e-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="9c53e-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c53e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c53e-116">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="9c53e-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="9c53e-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="9c53e-117">HttpGetUrl</span></span>  
 <span data-ttu-id="9c53e-118">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9c53e-118">Data type: string</span></span>  
  
 <span data-ttu-id="9c53e-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c53e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c53e-120">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c53e-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="9c53e-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="9c53e-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="9c53e-122">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="9c53e-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="9c53e-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c53e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c53e-124">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="9c53e-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="9c53e-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="9c53e-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="9c53e-126">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9c53e-126">Data type: string</span></span>  
  
 <span data-ttu-id="9c53e-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="9c53e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9c53e-128">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9c53e-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c53e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c53e-129">Requirements</span></span>  
  
|<span data-ttu-id="9c53e-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9c53e-130">MOF</span></span>|<span data-ttu-id="9c53e-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9c53e-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9c53e-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9c53e-132">Namespace</span></span>|<span data-ttu-id="9c53e-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9c53e-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c53e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c53e-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
