---
title: Página de ayuda del servicio web HTTP de WCF
ms.date: 03/30/2017
ms.assetid: 63c7c695-44b6-4f31-bb9c-00f2763f525e
ms.openlocfilehash: ef42457dea8bfe12a3e5054c5eacdf5a2964fdc7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600171"
---
# <a name="wcf-web-http-service-help-page"></a><span data-ttu-id="2486f-102">Página de ayuda del servicio web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="2486f-102">WCF Web HTTP Service Help Page</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="2486f-103">proporciona una página de ayuda automática para servicios WEB HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="2486f-103">provides an automatic help page for WCF WEB HTTP services.</span></span> <span data-ttu-id="2486f-104">Esta página de ayuda contiene una lista de descripciones de cada operación, formatos de solicitud y respuesta, así como esquemas.</span><span class="sxs-lookup"><span data-stu-id="2486f-104">This help page lists a description of each operation, request and response formats, and schemas.</span></span> <span data-ttu-id="2486f-105">Esta funcionalidad se desactiva de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="2486f-105">This functionality is turned off by default.</span></span> <span data-ttu-id="2486f-106">Cuando un usuario navega a un servicio WEB HTTP de WCF y anexa "/Help" al final de la dirección URL, por ejemplo `http://localhost:8000/Customers/Help` , se muestra una página de ayuda como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2486f-106">When a user browses to a WCF WEB HTTP service and appends "/Help" on to the end of the URL, for example `http://localhost:8000/Customers/Help`, a help page like the following is displayed.</span></span>  
  
 ![Un explorador con la página de ayuda de WCF REST abierta.](./media/wcf-web-http-service-help-page/windows-communication-foundation-rest-help-page.gif)  
  
 <span data-ttu-id="2486f-108">A continuación, el usuario puede hacer clic en cualquier método descrito en la página de ayuda para visualizar la página detallada de esa operación en la que se muestra más información sobre el método, incluidos formatos de mensajes y respuestas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2486f-108">The user can then click any method listed in the help page and detailed page for that operation is displayed showing more information about the method, including message formats and example responses.</span></span> <span data-ttu-id="2486f-109">La siguiente imagen es un ejemplo de una página de ayuda para un método.</span><span class="sxs-lookup"><span data-stu-id="2486f-109">The following image is an example of a help page for a method.</span></span>  
  
 ![Un explorador con los detalles de la página de ayuda de WCF REST para el método GetCustomers abierto.](./media/wcf-web-http-service-help-page/windows-communication-foundation-rest-help-page-detail.gif)  
  
## <a name="using-the-wcf-web-http-help-page"></a><span data-ttu-id="2486f-111">Utilizar la página de ayuda web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="2486f-111">Using the WCF Web HTTP Help Page</span></span>  
 <span data-ttu-id="2486f-112">La página de ayuda WEB HTTP de WCF muestra una breve descripción de cada operación siempre que haya especificado una con <xref:System.ComponentModel.DescriptionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2486f-112">The WCF WEB HTTP Help page displays a short description for each operation provided that you specify one using the <xref:System.ComponentModel.DescriptionAttribute>.</span></span> <span data-ttu-id="2486f-113">Este atributo toma una cadena que contiene una breve descripción de la operación a la que se aplica.</span><span class="sxs-lookup"><span data-stu-id="2486f-113">This attribute takes a string that contains a short description of the operation it is applied to.</span></span> <span data-ttu-id="2486f-114">Por ejemplo, el siguiente código muestra cómo utilizar <xref:System.ComponentModel.DescriptionAttribute> para proporcionar una breve descripción.</span><span class="sxs-lookup"><span data-stu-id="2486f-114">For example, the following code shows how to use the <xref:System.ComponentModel.DescriptionAttribute> to provide a short description.</span></span>  
  
```csharp
[OperationContract]  
[WebGet(UriTemplate="/template1", BodyStyle = WebMessageBodyStyle.Bare)]  
[Description("Description for GET /template1")]  
SyndicationFeedFormatter GetTemplate1();  
```  
  
 <span data-ttu-id="2486f-115">Para activar la página de ayuda WEB HTTP de WCF, debe agregar un comportamiento de punto de conexión a los puntos de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="2486f-115">To turn on the WCF WEB HTTP Help page, you must add an endpoint behavior to your service's endpoints.</span></span> <span data-ttu-id="2486f-116">Esto se puede hacer en la configuración o a través de un código.</span><span class="sxs-lookup"><span data-stu-id="2486f-116">This can be done in configuration or code.</span></span> <span data-ttu-id="2486f-117">Para habilitar la página de ayuda WEB HTTP de WCF en la configuración, agregue un comportamiento de extremo con un elemento `<webHttp>`, establezca `enableHelp` en `true` y agregue un extremo y configúrelo para utilizar el comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="2486f-117">To enable the WCF WEB HTTP Help age in configuration, add an endpoint behavior with a `<webHttp>` element, set `enableHelp` to `true`, and add an endpoint and configure it to use the endpoint behavior.</span></span> <span data-ttu-id="2486f-118">El código de configuración siguiente muestra cómo realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="2486f-118">The following configuration code shows how to do this.</span></span>  
  
```xml  
<endpointBehaviors>  
   <behavior name="RESTEndpointBehavior">  
      <webHttp enableHelp="true"/>  
   </behavior>  
</endpointBehaviors>  
<!-- ... -->  
<services>  
   <service behaviorConfiguration="RESTWebServiceBehavior" name="RESTWebService">      <endpoint address="" kind="webHttpEndpoint" behaviorConfiguration="RESTEndpointBehavior" contract="IHello" />  
  
      <!-- ... -->  
   </service>  
</services>  
```  
  
 <span data-ttu-id="2486f-119">Para habilitar la página de ayuda web HTTP de WCF a través de un código, agregue un extremo de servicio y agregue <xref:System.ServiceModel.Description.WebHttpBehavior> a la configuración de extremo <xref:System.ServiceModel.Description.WebHttpBehavior.HelpEnabled%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="2486f-119">To enable the WCF Web HTTP Help page in code, add a service endpoint and add a <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint setting <xref:System.ServiceModel.Description.WebHttpBehavior.HelpEnabled%2A> to `true`.</span></span> <span data-ttu-id="2486f-120">El código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="2486f-120">The following code shows how to do this.</span></span>  
  
```csharp
using (WebServiceHost host = new WebServiceHost(typeof(Service), new Uri("http://localhost:8000/Customers")))  
{  
   host.AddServiceEndpoint(typeof(ICustomerCollection), new WebHttpBinding(), "");
   host.Description.Endpoints[0].Behaviors.Add(new WebHttpBehavior { EnableHelp = true });  
   // ...  
}  
```  
  
 <span data-ttu-id="2486f-121">La página de ayuda se basa en XHTML con marcado que identifica las diferentes partes de la página.</span><span class="sxs-lookup"><span data-stu-id="2486f-121">The help page is XHTML based with mark-up that identifies the different parts of the page.</span></span> <span data-ttu-id="2486f-122">Esto permite a los clientes tener acceso mediante programación a la página mediante <xref:System.Xml.Linq.XElement> u otros API XLinq.</span><span class="sxs-lookup"><span data-stu-id="2486f-122">This enables clients to programmatically access the page using <xref:System.Xml.Linq.XElement> or other XLinq APIs.</span></span>  
  
## <a name="schemas-used-in-the-wcf-web-http-service-help-page"></a><span data-ttu-id="2486f-123">Esquemas empleados en la página de ayuda del servicio Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="2486f-123">Schemas Used in the WCF Web HTTP Service Help Page</span></span>  
 <span data-ttu-id="2486f-124">En la página de ayuda del servicio Web HTTP de WCF se emplean los siguientes esquemas.</span><span class="sxs-lookup"><span data-stu-id="2486f-124">The following schemas are used in the WCF Web HTTP service help page.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/" attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="anyType" nillable="true" type="xs:anyType" />  
  <xs:element name="anyURI" nillable="true" type="xs:anyURI" />  
  <xs:element name="base64Binary" nillable="true" type="xs:base64Binary" />  
  <xs:element name="boolean" nillable="true" type="xs:boolean" />  
  <xs:element name="byte" nillable="true" type="xs:byte" />  
  <xs:element name="dateTime" nillable="true" type="xs:dateTime" />  
  <xs:element name="decimal" nillable="true" type="xs:decimal" />  
  <xs:element name="double" nillable="true" type="xs:double" />  
  <xs:element name="float" nillable="true" type="xs:float" />  
  <xs:element name="int" nillable="true" type="xs:int" />  
  <xs:element name="long" nillable="true" type="xs:long" />  
  <xs:element name="QName" nillable="true" type="xs:QName" />  
  <xs:element name="short" nillable="true" type="xs:short" />  
  <xs:element name="string" nillable="true" type="xs:string" />  
  <xs:element name="unsignedByte" nillable="true" type="xs:unsignedByte" />  
  <xs:element name="unsignedInt" nillable="true" type="xs:unsignedInt" />  
  <xs:element name="unsignedLong" nillable="true" type="xs:unsignedLong" />  
  <xs:element name="unsignedShort" nillable="true" type="xs:unsignedShort" />  
  <xs:element name="char" nillable="true" type="tns:char" />  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:int" />  
  </xs:simpleType>  
  <xs:element name="duration" nillable="true" type="tns:duration" />  
  <xs:simpleType name="duration">  
    <xs:restriction base="xs:duration">  
      <xs:pattern value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?" />  
      <xs:minInclusive value="-P10675199DT2H48M5.4775808S" />  
      <xs:maxInclusive value="P10675199DT2H48M5.4775807S" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:element name="guid" nillable="true" type="tns:guid" />  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:attribute name="FactoryType" type="xs:QName" />  
  <xs:attribute name="Id" type="xs:ID" />  
  <xs:attribute name="Ref" type="xs:IDREF" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://microsoft.com/wsdl/types/" elementFormDefault="qualified" targetNamespace="http://microsoft.com/wsdl/types/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:unsignedShort" />  
  </xs:simpleType>  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.datacontract.org/2004/07/System" elementFormDefault="qualified" targetNamespace="http://schemas.datacontract.org/2004/07/System" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="DateTimeOffset">  
    <xs:annotation>  
      <xs:appinfo>  
        <IsValueType xmlns="http://schemas.microsoft.com/2003/10/Serialization/">true</IsValueType>  
      </xs:appinfo>  
    </xs:annotation>  
    <xs:sequence>  
      <xs:element name="DateTime" type="xs:dateTime" />  
      <xs:element name="OffsetMinutes" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="DateTimeOffset" nillable="true" type="tns:DateTimeOffset" />  
  <xs:complexType name="DBNull">  
    <xs:sequence />  
  </xs:complexType>  
  <xs:element name="DBNull" nillable="true" type="tns:DBNull" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:ser="http://schemas.microsoft.com/2003/10/Serialization/" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="ArrayOfboolean">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="boolean" type="xs:boolean" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfboolean" nillable="true" type="tns:ArrayOfboolean" />  
  <xs:complexType name="ArrayOfchar">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="char" type="ser:char" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfchar" nillable="true" type="tns:ArrayOfchar" />  
  <xs:complexType name="ArrayOfdateTime">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="dateTime" type="xs:dateTime" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdateTime" nillable="true" type="tns:ArrayOfdateTime" />  
  <xs:complexType name="ArrayOfdecimal">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="decimal" type="xs:decimal" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdecimal" nillable="true" type="tns:ArrayOfdecimal" />  
  <xs:complexType name="ArrayOfdouble">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="double" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdouble" nillable="true" type="tns:ArrayOfdouble" />  
  <xs:complexType name="ArrayOffloat">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="float" type="xs:float" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOffloat" nillable="true" type="tns:ArrayOffloat" />  
  <xs:complexType name="ArrayOfguid">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="guid" type="ser:guid" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfguid" nillable="true" type="tns:ArrayOfguid" />  
  <xs:complexType name="ArrayOfint">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="int" type="xs:int" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfint" nillable="true" type="tns:ArrayOfint" />  
  <xs:complexType name="ArrayOflong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="long" type="xs:long" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOflong" nillable="true" type="tns:ArrayOflong" />  
  <xs:complexType name="ArrayOfshort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="short" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfshort" nillable="true" type="tns:ArrayOfshort" />  
  <xs:complexType name="ArrayOfstring">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="string" nillable="true" type="xs:string" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfstring" nillable="true" type="tns:ArrayOfstring" />  
  <xs:complexType name="ArrayOfduration">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="duration" type="ser:duration" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfduration" nillable="true" type="tns:ArrayOfduration" />  
  <xs:complexType name="ArrayOfunsignedInt">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedInt" type="xs:unsignedInt" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedInt" nillable="true" type="tns:ArrayOfunsignedInt" />  
  <xs:complexType name="ArrayOfunsignedLong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedLong" type="xs:unsignedLong" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedLong" nillable="true" type="tns:ArrayOfunsignedLong" />  
  <xs:complexType name="ArrayOfunsignedShort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedShort" type="xs:unsignedShort" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedShort" nillable="true" type="tns:ArrayOfunsignedShort" />  
  <xs:complexType name="ArrayOfQName">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="QName" nillable="true" type="xs:QName" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfQName" nillable="true" type="tns:ArrayOfQName" />  
</xs:schema>  
```  
  
 <span data-ttu-id="2486f-125">Para obtener más información sobre el esquema de serialización de contrato de datos, vea [referencia de esquema de contrato de datos](data-contract-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2486f-125">For more information about the data contract serialization schema, see [Data Contract Schema Reference](data-contract-schema-reference.md).</span></span>
