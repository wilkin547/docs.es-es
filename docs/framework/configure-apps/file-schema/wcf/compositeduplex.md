---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a5209efddd489f8cb04b3266e6ba0bb033eeae6c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176024"
---
# \<compositeDuplex>

<span data-ttu-id="2b7b9-101">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="2b7b9-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b7b9-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b7b9-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2b7b9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2b7b9-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b7b9-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="2b7b9-105">Attributes</span></span>  
  
|<span data-ttu-id="2b7b9-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="2b7b9-106">Attribute</span></span>|<span data-ttu-id="2b7b9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7b9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b7b9-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="2b7b9-108">clientBaseAddress</span></span>|<span data-ttu-id="2b7b9-109">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="2b7b9-110">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="2b7b9-111">Si no se establece este atributo, se genera una dirección predeterminada " `full qualified name+default port\TemporaryIndigoAddress\guid` ".</span><span class="sxs-lookup"><span data-stu-id="2b7b9-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="2b7b9-112">El valor predeterminado es `null`.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b7b9-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2b7b9-113">Child Elements</span></span>  

 <span data-ttu-id="2b7b9-114">None</span><span class="sxs-lookup"><span data-stu-id="2b7b9-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b7b9-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2b7b9-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2b7b9-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2b7b9-116">Element</span></span>|<span data-ttu-id="2b7b9-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b7b9-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="2b7b9-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b7b9-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2b7b9-119">Remarks</span></span>  

 <span data-ttu-id="2b7b9-120">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="2b7b9-121">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="2b7b9-122">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="2b7b9-123">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="2b7b9-124">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b7b9-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b7b9-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="2b7b9-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b7b9-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2b7b9-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="2b7b9-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2b7b9-128">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="2b7b9-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2b7b9-129">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2b7b9-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
