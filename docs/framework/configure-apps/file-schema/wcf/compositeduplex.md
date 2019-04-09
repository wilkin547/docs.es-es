---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: 1e5ecc2b937aa0cdb159a6cbd1222fe6d4af79fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159853"
---
# <a name="compositeduplex"></a><span data-ttu-id="b66fe-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="b66fe-101">\<compositeDuplex></span></span>
<span data-ttu-id="b66fe-102">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="b66fe-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="b66fe-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b66fe-103">\<system.serviceModel></span></span>  
<span data-ttu-id="b66fe-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b66fe-104">\<bindings></span></span>  
<span data-ttu-id="b66fe-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b66fe-105">\<customBinding></span></span>  
<span data-ttu-id="b66fe-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b66fe-106">\<binding></span></span>  
<span data-ttu-id="b66fe-107">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="b66fe-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66fe-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b66fe-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b66fe-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b66fe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b66fe-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b66fe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b66fe-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="b66fe-111">Attributes</span></span>  
  
|<span data-ttu-id="b66fe-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="b66fe-112">Attribute</span></span>|<span data-ttu-id="b66fe-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b66fe-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b66fe-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="b66fe-114">clientBaseAddress</span></span>|<span data-ttu-id="b66fe-115">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="b66fe-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="b66fe-116">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="b66fe-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="b66fe-117">Si este atributo no se establece, una dirección predeterminada "`full qualified name+default port\TemporaryIndigoAddress\guid`" se genera.</span><span class="sxs-lookup"><span data-stu-id="b66fe-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="b66fe-118">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="b66fe-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b66fe-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b66fe-119">Child Elements</span></span>  
 <span data-ttu-id="b66fe-120">Ninguna</span><span class="sxs-lookup"><span data-stu-id="b66fe-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b66fe-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b66fe-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b66fe-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b66fe-122">Element</span></span>|<span data-ttu-id="b66fe-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b66fe-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b66fe-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="b66fe-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b66fe-125">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="b66fe-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b66fe-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b66fe-126">Remarks</span></span>  
 <span data-ttu-id="b66fe-127">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="b66fe-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="b66fe-128">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="b66fe-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="b66fe-129">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="b66fe-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="b66fe-130">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="b66fe-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="b66fe-131">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="b66fe-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b66fe-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b66fe-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b66fe-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b66fe-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b66fe-134">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b66fe-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b66fe-135">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="b66fe-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b66fe-136">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="b66fe-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b66fe-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b66fe-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
