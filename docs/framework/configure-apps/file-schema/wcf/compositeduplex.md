---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736777"
---
# <a name="compositeduplex"></a><span data-ttu-id="9c33f-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="9c33f-101">\<compositeDuplex></span></span>
<span data-ttu-id="9c33f-102">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="9c33f-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="9c33f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9c33f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9c33f-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9c33f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9c33f-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="9c33f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9c33f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="9c33f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="9c33f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="9c33f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9c33f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<compositeDuplex >**</span><span class="sxs-lookup"><span data-stu-id="9c33f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c33f-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c33f-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c33f-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c33f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9c33f-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c33f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c33f-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c33f-112">Attributes</span></span>  
  
|<span data-ttu-id="9c33f-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c33f-113">Attribute</span></span>|<span data-ttu-id="9c33f-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c33f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c33f-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="9c33f-115">clientBaseAddress</span></span>|<span data-ttu-id="9c33f-116">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="9c33f-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="9c33f-117">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9c33f-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="9c33f-118">Si no se establece este atributo, se genera una dirección predeterminada "`full qualified name+default port\TemporaryIndigoAddress\guid`".</span><span class="sxs-lookup"><span data-stu-id="9c33f-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="9c33f-119">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="9c33f-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c33f-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c33f-120">Child Elements</span></span>  
 <span data-ttu-id="9c33f-121">Ninguno</span><span class="sxs-lookup"><span data-stu-id="9c33f-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c33f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c33f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9c33f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c33f-123">Element</span></span>|<span data-ttu-id="9c33f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c33f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c33f-125">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="9c33f-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="9c33f-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9c33f-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c33f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c33f-127">Remarks</span></span>  
 <span data-ttu-id="9c33f-128">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="9c33f-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="9c33f-129">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="9c33f-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="9c33f-130">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="9c33f-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="9c33f-131">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="9c33f-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="9c33f-132">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="9c33f-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c33f-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c33f-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="9c33f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c33f-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9c33f-135">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9c33f-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9c33f-136">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9c33f-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9c33f-137">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9c33f-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9c33f-138">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9c33f-138">\<customBinding></span></span>](custombinding.md)
