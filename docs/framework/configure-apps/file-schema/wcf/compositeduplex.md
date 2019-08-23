---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: e79b3e1aeecc52bf41ae759dc15ebf1c8211beb2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926064"
---
# <a name="compositeduplex"></a><span data-ttu-id="88200-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="88200-101">\<compositeDuplex></span></span>
<span data-ttu-id="88200-102">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="88200-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="88200-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="88200-103">\<system.serviceModel></span></span>  
<span data-ttu-id="88200-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="88200-104">\<bindings></span></span>  
<span data-ttu-id="88200-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="88200-105">\<customBinding></span></span>  
<span data-ttu-id="88200-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="88200-106">\<binding></span></span>  
<span data-ttu-id="88200-107">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="88200-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88200-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88200-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88200-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="88200-109">Attributes and Elements</span></span>  
 <span data-ttu-id="88200-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="88200-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88200-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="88200-111">Attributes</span></span>  
  
|<span data-ttu-id="88200-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="88200-112">Attribute</span></span>|<span data-ttu-id="88200-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="88200-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88200-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="88200-114">clientBaseAddress</span></span>|<span data-ttu-id="88200-115">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="88200-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="88200-116">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="88200-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="88200-117">Si no se establece este atributo, se genera una dirección`full qualified name+default port\TemporaryIndigoAddress\guid`predeterminada "".</span><span class="sxs-lookup"><span data-stu-id="88200-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="88200-118">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="88200-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88200-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="88200-119">Child Elements</span></span>  
 <span data-ttu-id="88200-120">None</span><span class="sxs-lookup"><span data-stu-id="88200-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88200-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="88200-121">Parent Elements</span></span>  
  
|<span data-ttu-id="88200-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="88200-122">Element</span></span>|<span data-ttu-id="88200-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="88200-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88200-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="88200-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="88200-125">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="88200-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88200-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="88200-126">Remarks</span></span>  
 <span data-ttu-id="88200-127">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="88200-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="88200-128">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="88200-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="88200-129">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="88200-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="88200-130">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="88200-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="88200-131">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="88200-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88200-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88200-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="88200-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="88200-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="88200-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="88200-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="88200-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="88200-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="88200-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="88200-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="88200-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="88200-137">\<customBinding></span></span>](custombinding.md)
