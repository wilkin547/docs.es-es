---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768662"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="82703-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="82703-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="82703-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="82703-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82703-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82703-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="82703-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="82703-105">Methods</span></span>  
 <span data-ttu-id="82703-106">La clase ServiceDebugBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="82703-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="82703-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="82703-107">Properties</span></span>  
 <span data-ttu-id="82703-108">La clase ServiceDebugBehavior posee las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="82703-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="82703-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="82703-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="82703-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="82703-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="82703-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="82703-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82703-112">Controla si el servicio publica su WSDL en la dirección controlada por el atributo `HttpGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="82703-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="82703-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="82703-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="82703-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="82703-114">Data type: string</span></span>  
  
 <span data-ttu-id="82703-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="82703-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82703-116">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTP.</span><span class="sxs-lookup"><span data-stu-id="82703-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="82703-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="82703-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="82703-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="82703-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="82703-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="82703-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82703-120">Controla si el servicio publica su WSDL sobre HTTPS en la dirección controlada por el atributo `HttpsGetUrl`.</span><span class="sxs-lookup"><span data-stu-id="82703-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="82703-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="82703-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="82703-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="82703-122">Data type: string</span></span>  
  
 <span data-ttu-id="82703-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="82703-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82703-124">Establece la ubicación en la que el WSDL del servicio se publica para la recuperación mediante HTTPS.</span><span class="sxs-lookup"><span data-stu-id="82703-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="82703-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="82703-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="82703-126">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="82703-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="82703-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="82703-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="82703-128">Especifica si incluir la información de excepción administrada en el detalle de errores  SOAP devueltos a los clientes para depuración.</span><span class="sxs-lookup"><span data-stu-id="82703-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82703-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="82703-129">Requirements</span></span>  
  
|<span data-ttu-id="82703-130">MOF</span><span class="sxs-lookup"><span data-stu-id="82703-130">MOF</span></span>|<span data-ttu-id="82703-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="82703-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="82703-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="82703-132">Namespace</span></span>|<span data-ttu-id="82703-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="82703-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82703-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="82703-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
