---
title: Interoperabilidad con servicios web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: f38209ffe2161e58528a108b29e730665a65da37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598871"
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="796ad-102">Interoperabilidad con servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="796ad-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="796ad-103">La interoperabilidad entre los servicios Web de ASP.NET y los servicios Web de Windows Communication Foundation (WCF) se puede lograr asegurándose de que los servicios implementados mediante ambas tecnologías se ajusten a la especificación de WS-I Basic Profile 1,1.</span><span class="sxs-lookup"><span data-stu-id="796ad-103">Interoperability between ASP.NET Web services and Windows Communication Foundation (WCF) Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> <span data-ttu-id="796ad-104">Los servicios Web de ASP.NET que cumplen con WS-I Basic Profile 1,1 son interoperables con los clientes de WCF mediante el enlace proporcionado por el sistema WCF, <xref:System.ServiceModel.BasicHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="796ad-104">ASP.NET Web services that conform to WS-I Basic Profile 1.1 are interoperable with WCF clients by using WCF system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="796ad-105">Use la opción ASP.NET 2,0 de agregar <xref:System.Web.Services.WebService> los <xref:System.Web.Services.WebMethodAttribute> atributos y a una interfaz en lugar de a una clase, y escriba una clase para implementar la interfaz, tal como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="796ad-105">Use ASP.NET 2.0 option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
```csharp
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
  
 <span data-ttu-id="796ad-106">El uso de esta opción es preferible, porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.</span><span class="sxs-lookup"><span data-stu-id="796ad-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="796ad-107">Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="796ad-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="796ad-108">WCF usa el `SOAPAction` encabezado HTTP para enrutar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="796ad-108">WCF uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="796ad-109">El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente.</span><span class="sxs-lookup"><span data-stu-id="796ad-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="796ad-110">Al definir un tipo de datos para su uso con ASP. NETWeb Services en previsión de adoptar WCF, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="796ad-110">When defining a data type for use with ASP.NETWeb services in anticipation of adopting WCF, do the following:</span></span>  
  
- <span data-ttu-id="796ad-111">Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.</span><span class="sxs-lookup"><span data-stu-id="796ad-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
- <span data-ttu-id="796ad-112">Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo.</span><span class="sxs-lookup"><span data-stu-id="796ad-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="796ad-113">No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.</span><span class="sxs-lookup"><span data-stu-id="796ad-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
- <span data-ttu-id="796ad-114">Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión.</span><span class="sxs-lookup"><span data-stu-id="796ad-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="796ad-115">Los tipos que se usan en los mensajes de los servicios Web ASP.NET pueden procesarse como contratos de datos por parte de las aplicaciones WCF, produciendo, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="796ad-115">The types used in messages by ASP.NET Web services can be processed as data contracts by WCF applications, yielding, among other benefits, better performance in WCF applications.</span></span>  
  
 <span data-ttu-id="796ad-116">Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="796ad-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="796ad-117">Los clientes de WCF no las admiten.</span><span class="sxs-lookup"><span data-stu-id="796ad-117">WCF clients do not support them.</span></span> <span data-ttu-id="796ad-118">Si se debe proteger un servicio, utilice las opciones proporcionadas por WCF, ya que estas opciones son sólidas y se basan en protocolos estándar.</span><span class="sxs-lookup"><span data-stu-id="796ad-118">If a service must be secured, use the options provided by WCF, because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="796ad-119">Repercusión en el rendimiento de la carga de ServiceModel HttpModule</span><span class="sxs-lookup"><span data-stu-id="796ad-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="796ad-120">En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF.</span><span class="sxs-lookup"><span data-stu-id="796ad-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="796ad-121">Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="796ad-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a><span data-ttu-id="796ad-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="796ad-122">See also</span></span>

- [<span data-ttu-id="796ad-123">Procedimiento para configurar servicios WCF para interoperar con clientes de servicios web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="796ad-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](config-wcf-service-with-aspnet-web-service.md)
