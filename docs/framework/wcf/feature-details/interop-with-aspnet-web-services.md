---
title: Interoperabilidad con servicios web ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef174f457114003e5b2783b50040424d9a96945c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="c9de8-102">Interoperabilidad con servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c9de8-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="c9de8-103">La interoperabilidad entre los servicio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y los servicio web de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se puede lograr asegurando que los servicios implementados usen ambas tecnologías de acuerdo con la especificación WS-I Basic Profile 1.1.</span><span class="sxs-lookup"><span data-stu-id="c9de8-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> <span data-ttu-id="c9de8-104">Los servicio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que cumplen con WS-I Basic Profile 1.1 son interoperables con clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante el uso de enlace proporcionado por el sistema de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c9de8-104">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services that conform to WS-I Basic Profile 1.1 are interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="c9de8-105">Utilice la opción de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] de agregar los atributos <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase y escribir una clase para implementar la interfaz, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9de8-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="c9de8-106">El uso de esta opción es preferible, porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.</span><span class="sxs-lookup"><span data-stu-id="c9de8-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="c9de8-107">Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="c9de8-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c9de8-108"> usa el encabezado HTTP `SOAPAction` para enrutar mensajes.</span><span class="sxs-lookup"><span data-stu-id="c9de8-108"> uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="c9de8-109">El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente.</span><span class="sxs-lookup"><span data-stu-id="c9de8-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="c9de8-110">Al definir un tipo de datos para su uso con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]servicios Web de prever la adopción [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c9de8-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], do the following:</span></span>  
  
-   <span data-ttu-id="c9de8-111">Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.</span><span class="sxs-lookup"><span data-stu-id="c9de8-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="c9de8-112">Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo.</span><span class="sxs-lookup"><span data-stu-id="c9de8-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="c9de8-113">No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.</span><span class="sxs-lookup"><span data-stu-id="c9de8-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="c9de8-114">Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión.</span><span class="sxs-lookup"><span data-stu-id="c9de8-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="c9de8-115">Los tipos utilizados en los mensajes por los servicios web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se pueden procesar como contratos de datos a través de aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], lo que produce, entre otras ventajas, un mejor rendimiento en las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9de8-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, among other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="c9de8-116">Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="c9de8-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="c9de8-117">Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no las admiten.</span><span class="sxs-lookup"><span data-stu-id="c9de8-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="c9de8-118">Si es necesario proteger un servicio, utilice las opciones proporcionadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], porque estas opciones son robustas y se basan en protocolos estándar.</span><span class="sxs-lookup"><span data-stu-id="c9de8-118">If a service must be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="c9de8-119">Repercusión en el rendimiento de la carga de ServiceModel HttpModule</span><span class="sxs-lookup"><span data-stu-id="c9de8-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="c9de8-120">En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF.</span><span class="sxs-lookup"><span data-stu-id="c9de8-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="c9de8-121">Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c9de8-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9de8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9de8-122">See Also</span></span>  
 [<span data-ttu-id="c9de8-123">Configuración de servicios WCF para interoperar con clientes de servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c9de8-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
