---
description: 'Más información acerca de: ServiceMetadataBehavior'
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1b1438013ec667b10b300d898687abf6f33f96fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715488"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="88262-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="88262-103">ServiceMetadataBehavior</span></span>

<span data-ttu-id="88262-104">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="88262-104">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88262-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88262-105">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="88262-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="88262-106">Methods</span></span>  

 <span data-ttu-id="88262-107">La clase ServiceMetadataBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="88262-107">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="88262-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="88262-108">Properties</span></span>  

 <span data-ttu-id="88262-109">La clase ServiceMetadataBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="88262-109">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="88262-110">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="88262-110">ExternalMetadataLocation</span></span>  

 <span data-ttu-id="88262-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88262-111">Data type: string</span></span>  
  
 <span data-ttu-id="88262-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88262-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88262-113">Establece la ubicación a la que el servicio redirige las solicitudes de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="88262-113">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="88262-114">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="88262-114">HttpGetEnabled</span></span>  

 <span data-ttu-id="88262-115">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88262-115">Data type: boolean</span></span>  
  
 <span data-ttu-id="88262-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88262-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88262-117">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="88262-117">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="88262-118">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="88262-118">HttpGetUrl</span></span>  

 <span data-ttu-id="88262-119">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88262-119">Data type: string</span></span>  
  
 <span data-ttu-id="88262-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88262-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88262-121">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="88262-121">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="88262-122">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="88262-122">HttpsGetEnabled</span></span>  

 <span data-ttu-id="88262-123">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="88262-123">Data type: boolean</span></span>  
  
 <span data-ttu-id="88262-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88262-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88262-125">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="88262-125">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="88262-126">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="88262-126">HttpsGetUrl</span></span>  

 <span data-ttu-id="88262-127">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="88262-127">Data type: string</span></span>  
  
 <span data-ttu-id="88262-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="88262-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="88262-129">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="88262-129">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88262-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="88262-130">Requirements</span></span>  
  
|<span data-ttu-id="88262-131">MOF</span><span class="sxs-lookup"><span data-stu-id="88262-131">MOF</span></span>|<span data-ttu-id="88262-132">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="88262-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="88262-133">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="88262-133">Namespace</span></span>|<span data-ttu-id="88262-134">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="88262-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88262-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="88262-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
