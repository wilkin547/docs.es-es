---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d6b866c90e3e6c6e72dc75f230bcf7b4e03a6bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="63f74-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="63f74-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="63f74-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="63f74-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f74-104">Syntax</span></span>  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="63f74-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="63f74-105">Methods</span></span>  
 <span data-ttu-id="63f74-106">La clase ServiceDebugBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="63f74-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="63f74-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="63f74-107">Properties</span></span>  
 <span data-ttu-id="63f74-108">La clase ServiceDebugBehavior posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="63f74-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="63f74-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="63f74-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="63f74-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="63f74-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="63f74-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="63f74-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63f74-112">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="63f74-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="63f74-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="63f74-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="63f74-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="63f74-114">Data type: string</span></span>  
  
 <span data-ttu-id="63f74-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="63f74-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63f74-116">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="63f74-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="63f74-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="63f74-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="63f74-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="63f74-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="63f74-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="63f74-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63f74-120">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="63f74-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="63f74-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="63f74-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="63f74-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="63f74-122">Data type: string</span></span>  
  
 <span data-ttu-id="63f74-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="63f74-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63f74-124">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="63f74-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="63f74-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="63f74-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="63f74-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="63f74-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="63f74-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="63f74-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="63f74-128">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="63f74-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63f74-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63f74-129">Requirements</span></span>  
  
|<span data-ttu-id="63f74-130">MOF</span><span class="sxs-lookup"><span data-stu-id="63f74-130">MOF</span></span>|<span data-ttu-id="63f74-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="63f74-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="63f74-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="63f74-132">Namespace</span></span>|<span data-ttu-id="63f74-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="63f74-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63f74-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="63f74-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
