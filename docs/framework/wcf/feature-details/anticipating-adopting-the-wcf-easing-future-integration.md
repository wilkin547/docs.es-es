---
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: ead28354a3687bcca22a1a0eb5ccc9f15f0c69d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266576"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="72081-102">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración</span><span class="sxs-lookup"><span data-stu-id="72081-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>

<span data-ttu-id="72081-103">Si usa ASP.NET hoy y prevé usar WCF en el futuro, en este tema se proporcionan instrucciones para asegurarse de que los nuevos servicios Web de ASP.NET funcionarán bien junto con las aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="72081-103">If you use ASP.NET today, and anticipate using WCF in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with WCF applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="72081-104">Recomendaciones generales</span><span class="sxs-lookup"><span data-stu-id="72081-104">General Recommendations</span></span>  

 <span data-ttu-id="72081-105">Adopte ASP.NET 2.0 para cualquier nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="72081-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="72081-106">Al hacer esto, se proporcionará acceso a las mejoras y ampliaciones de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="72081-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="72081-107">Sin embargo, también permitirá la posibilidad de usar componentes de ASP.NET 2,0 junto con componentes de WCF en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="72081-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with WCF components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="72081-108">Protocolos</span><span class="sxs-lookup"><span data-stu-id="72081-108">Protocols</span></span>  

 <span data-ttu-id="72081-109">Use la nueva facilidad de ASP.NET 2.0 para validar la conformidad con WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="72081-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="72081-110">Los servicios Web de ASP.NET que cumplen con WS-I Basic Profile 1,1 serán interoperables con los clientes de WCF mediante el enlace predefinido de WCF <xref:System.ServiceModel.BasicHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="72081-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with WCF clients by using WCF predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="72081-111">Desarrollo del servicio</span><span class="sxs-lookup"><span data-stu-id="72081-111">Service Development</span></span>  

 <span data-ttu-id="72081-112">Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP SOAPAction.</span><span class="sxs-lookup"><span data-stu-id="72081-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> <span data-ttu-id="72081-113">WCF usa el encabezado HTTP SOAPAction para enrutar mensajes.</span><span class="sxs-lookup"><span data-stu-id="72081-113">WCF uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="72081-114">Representación de datos</span><span class="sxs-lookup"><span data-stu-id="72081-114">Data Representation</span></span>  

 <span data-ttu-id="72081-115">El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente.</span><span class="sxs-lookup"><span data-stu-id="72081-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="72081-116">Al definir un tipo de datos para su uso con los servicios Web de ASP.NET en previsión de adoptar WCF en el futuro, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="72081-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting WCF in the future, do the following:</span></span>  
  
1. <span data-ttu-id="72081-117">Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.</span><span class="sxs-lookup"><span data-stu-id="72081-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2. <span data-ttu-id="72081-118">Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo.</span><span class="sxs-lookup"><span data-stu-id="72081-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="72081-119">No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.</span><span class="sxs-lookup"><span data-stu-id="72081-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="72081-120">Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión.</span><span class="sxs-lookup"><span data-stu-id="72081-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="72081-121">Los tipos que se usan en los mensajes de los servicios Web de ASP.NET se podrán procesar como contratos de datos por parte de las aplicaciones WCF, produciendo, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="72081-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by WCF applications, yielding, amongst other benefits, better performance in WCF applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="72081-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="72081-122">Security</span></span>  

 <span data-ttu-id="72081-123">Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="72081-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="72081-124">Los clientes de WCF no las admiten.</span><span class="sxs-lookup"><span data-stu-id="72081-124">WCF clients do not support them.</span></span> <span data-ttu-id="72081-125">Si es necesario proteger un servicio, utilice las opciones proporcionadas por WCF, ya que estas opciones son más enriquecidas y se basan en protocolos estándar.</span><span class="sxs-lookup"><span data-stu-id="72081-125">If a service needs to be secured, use the options provided by WCF, because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72081-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="72081-126">See also</span></span>

- [<span data-ttu-id="72081-127">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración</span><span class="sxs-lookup"><span data-stu-id="72081-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](anticipating-adopting-wcf-migration.md)
