---
description: 'Más información acerca de: ServiceDebugBehavior'
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 3b384c209524267c72a12d96bc845b694144ba19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715540"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="16d95-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="16d95-103">ServiceDebugBehavior</span></span>

<span data-ttu-id="16d95-104">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="16d95-104">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d95-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16d95-105">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="16d95-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="16d95-106">Methods</span></span>  

 <span data-ttu-id="16d95-107">La clase ServiceDebugBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="16d95-107">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="16d95-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="16d95-108">Properties</span></span>  

 <span data-ttu-id="16d95-109">La clase ServiceDebugBehavior posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="16d95-109">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="16d95-110">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="16d95-110">HttpHelpPageEnabled</span></span>  

 <span data-ttu-id="16d95-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="16d95-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="16d95-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="16d95-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16d95-113">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="16d95-113">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="16d95-114">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="16d95-114">HttpHelpPageUrl</span></span>  

 <span data-ttu-id="16d95-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="16d95-115">Data type: string</span></span>  
  
 <span data-ttu-id="16d95-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="16d95-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16d95-117">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="16d95-117">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="16d95-118">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="16d95-118">HttpsHelpPageEnabled</span></span>  

 <span data-ttu-id="16d95-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="16d95-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="16d95-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="16d95-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16d95-121">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="16d95-121">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="16d95-122">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="16d95-122">HttpsHelpPageUrl</span></span>  

 <span data-ttu-id="16d95-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="16d95-123">Data type: string</span></span>  
  
 <span data-ttu-id="16d95-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="16d95-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16d95-125">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="16d95-125">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="16d95-126">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="16d95-126">IncludeExceptionDetailInFaults</span></span>  

 <span data-ttu-id="16d95-127">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="16d95-127">Data type: boolean</span></span>  
  
 <span data-ttu-id="16d95-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="16d95-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="16d95-129">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="16d95-129">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16d95-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16d95-130">Requirements</span></span>  
  
|<span data-ttu-id="16d95-131">MOF</span><span class="sxs-lookup"><span data-stu-id="16d95-131">MOF</span></span>|<span data-ttu-id="16d95-132">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="16d95-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="16d95-133">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="16d95-133">Namespace</span></span>|<span data-ttu-id="16d95-134">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="16d95-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16d95-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="16d95-135">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
