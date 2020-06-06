---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736777"
---
# \<compositeDuplex>
<span data-ttu-id="9dd5f-101">Define el elemento de enlace que se usa cuando el cliente debe exponer un punto de conexión para que el servicio devuelva los mensajes al cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="9dd5f-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dd5f-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9dd5f-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9dd5f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="9dd5f-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9dd5f-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="9dd5f-105">Attributes</span></span>  
  
|<span data-ttu-id="9dd5f-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="9dd5f-106">Attribute</span></span>|<span data-ttu-id="9dd5f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dd5f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9dd5f-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="9dd5f-108">clientBaseAddress</span></span>|<span data-ttu-id="9dd5f-109">Un URI que establece la dirección del canal secundario en modo de dúplex.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="9dd5f-110">El servicio usa esta dirección para hacer contacto y establecer una conexión con el cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="9dd5f-111">Si no se establece este atributo, se genera una dirección predeterminada " `full qualified name+default port\TemporaryIndigoAddress\guid` ".</span><span class="sxs-lookup"><span data-stu-id="9dd5f-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="9dd5f-112">De manera predeterminada, es `null`.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9dd5f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9dd5f-113">Child Elements</span></span>  
 <span data-ttu-id="9dd5f-114">None</span><span class="sxs-lookup"><span data-stu-id="9dd5f-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9dd5f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9dd5f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="9dd5f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9dd5f-116">Element</span></span>|<span data-ttu-id="9dd5f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dd5f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="9dd5f-118">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dd5f-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dd5f-119">Remarks</span></span>  
 <span data-ttu-id="9dd5f-120">Este elemento de configuración se utiliza con los transportes que no permiten nativamente las comunicaciones dúplex, por ejemplo, HTTP.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="9dd5f-121">TCP, en cambio, permite comunicaciones dúplex de manera nativa y no requiere el uso de este elemento de enlace para que el servicio devuelva los mensajes a un cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="9dd5f-122">El cliente debe exponer una dirección para que el servicio haga contacto y establezca una conexión.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="9dd5f-123">El atributo `clientBaseAddress` proporciona esta dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="9dd5f-124">Observe que Windows Communication Foundation (WCF) genera automáticamente una ClientBaseAddress, si el usuario no establece explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="9dd5f-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dd5f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9dd5f-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="9dd5f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9dd5f-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9dd5f-127">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9dd5f-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9dd5f-128">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9dd5f-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9dd5f-129">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9dd5f-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
