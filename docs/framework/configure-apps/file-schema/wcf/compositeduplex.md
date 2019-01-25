---
title: '&lt;compositeDuplex&gt;'
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: e00cc6f3214dc9a040a9b6170271b1f4188d1631
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601628"
---
# <a name="ltcompositeduplexgt"></a><span data-ttu-id="14e9e-102">&lt;compositeDuplex&gt;</span><span class="sxs-lookup"><span data-stu-id="14e9e-102">&lt;compositeDuplex&gt;</span></span>
<span data-ttu-id="14e9e-103">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="14e9e-103">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="14e9e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="14e9e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="14e9e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="14e9e-105">\<bindings></span></span>  
<span data-ttu-id="14e9e-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="14e9e-106">\<customBinding></span></span>  
<span data-ttu-id="14e9e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="14e9e-107">\<binding></span></span>  
<span data-ttu-id="14e9e-108">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="14e9e-108">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e9e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14e9e-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e9e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14e9e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14e9e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14e9e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e9e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="14e9e-112">Attributes</span></span>  
  
|<span data-ttu-id="14e9e-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="14e9e-113">Attribute</span></span>|<span data-ttu-id="14e9e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="14e9e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14e9e-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="14e9e-115">clientBaseAddress</span></span>|<span data-ttu-id="14e9e-116">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="14e9e-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="14e9e-117">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="14e9e-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="14e9e-118">Si este atributo no se establece, una dirección predeterminada "`full qualified name+default port\TemporaryIndigoAddress\guid`" se genera.</span><span class="sxs-lookup"><span data-stu-id="14e9e-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="14e9e-119">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="14e9e-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e9e-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14e9e-120">Child Elements</span></span>  
 <span data-ttu-id="14e9e-121">Ninguna</span><span class="sxs-lookup"><span data-stu-id="14e9e-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14e9e-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14e9e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="14e9e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="14e9e-123">Element</span></span>|<span data-ttu-id="14e9e-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="14e9e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e9e-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="14e9e-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="14e9e-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="14e9e-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e9e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14e9e-127">Remarks</span></span>  
 <span data-ttu-id="14e9e-128">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="14e9e-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="14e9e-129">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="14e9e-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="14e9e-130">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="14e9e-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="14e9e-131">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="14e9e-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="14e9e-132">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="14e9e-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14e9e-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14e9e-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="14e9e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="14e9e-134">See also</span></span>
- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="14e9e-135">Enlaces</span><span class="sxs-lookup"><span data-stu-id="14e9e-135">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="14e9e-136">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="14e9e-136">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="14e9e-137">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="14e9e-137">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="14e9e-138">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="14e9e-138">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
