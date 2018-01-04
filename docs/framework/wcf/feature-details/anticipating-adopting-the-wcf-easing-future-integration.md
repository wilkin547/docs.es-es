---
title: "Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8dbb50af9d5655a76abb3827cd2f512eab0fd662
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="e2ac8-102">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración</span><span class="sxs-lookup"><span data-stu-id="e2ac8-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="e2ac8-103">Si utiliza ASP.NET hoy, y prevé que utilizará [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el futuro, este tema proporciona la orientación para garantizar que los nuevos servicios web ASP.NET funcionarán bien junto con las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2ac8-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="e2ac8-104">Recomendaciones generales</span><span class="sxs-lookup"><span data-stu-id="e2ac8-104">General Recommendations</span></span>  
 <span data-ttu-id="e2ac8-105">Adopte ASP.NET 2.0 para cualquier nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="e2ac8-106">Al hacer esto, se proporcionará acceso a las mejoras y ampliaciones de la nueva versión.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="e2ac8-107">Sin embargo, también permitirá la posibilidad de utilizar los componentes de ASP.NET 2.0 junto con los componentes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en la misma aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="e2ac8-108">Protocolos</span><span class="sxs-lookup"><span data-stu-id="e2ac8-108">Protocols</span></span>  
 <span data-ttu-id="e2ac8-109">Use la nueva facilidad de ASP.NET 2.0 para validar la conformidad con WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="e2ac8-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="e2ac8-110">Los servicios web ASP.NET que cumplen con WS-I Basic Profile 1.1 serán interoperables con clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando el enlace predefinido de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="e2ac8-111">Desarrollo del servicio</span><span class="sxs-lookup"><span data-stu-id="e2ac8-111">Service Development</span></span>  
 <span data-ttu-id="e2ac8-112">Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP SOAPAction.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e2ac8-113"> usa el encabezado HTTP SOAPAction para enrutar mensajes.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-113"> uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="e2ac8-114">Representación de datos</span><span class="sxs-lookup"><span data-stu-id="e2ac8-114">Data Representation</span></span>  
 <span data-ttu-id="e2ac8-115">El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="e2ac8-116">Al definir un tipo de datos para el uso con servicios web ASP.NET al prever la adopción en el futuro de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2ac8-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="e2ac8-117">Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="e2ac8-118">Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="e2ac8-119">No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="e2ac8-120">Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="e2ac8-121">Los tipos utilizados en mensajes por los servicios web ASP.NET podrán ser procesados como contratos de datos mediante aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], proporcionando, entre otras ventajas, un mejor rendimiento en aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2ac8-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="e2ac8-122">Seguridad</span><span class="sxs-lookup"><span data-stu-id="e2ac8-122">Security</span></span>  
 <span data-ttu-id="e2ac8-123">Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="e2ac8-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="e2ac8-124">Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no las admiten.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="e2ac8-125">Si es necesario proteger un servicio, utilice las opciones proporcionadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], porque estas opciones son mejores y se basan en protocolos estándar.</span><span class="sxs-lookup"><span data-stu-id="e2ac8-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2ac8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ac8-126">See Also</span></span>  
 [<span data-ttu-id="e2ac8-127">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración</span><span class="sxs-lookup"><span data-stu-id="e2ac8-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
