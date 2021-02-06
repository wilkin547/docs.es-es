---
description: 'Más información acerca de cómo anticiparse a la adopción del Windows Communication Foundation: facilitar la migración futura'
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 6ea81b1dd01ed45ff62fa50c1b17442f88fc05af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643818"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="c40e1-103">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración</span><span class="sxs-lookup"><span data-stu-id="c40e1-103">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>

<span data-ttu-id="c40e1-104">Para garantizar una migración futura más sencilla de las nuevas aplicaciones de ASP.NET a WCF, siga las recomendaciones anteriores, así como las recomendaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="c40e1-104">To ensure an easier future migration of new ASP.NET applications to WCF, follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="c40e1-105">Protocolos</span><span class="sxs-lookup"><span data-stu-id="c40e1-105">Protocols</span></span>  

 <span data-ttu-id="c40e1-106">Deshabilite la compatibilidad de ASP.NET 2.0 para SOAP 1.2:</span><span class="sxs-lookup"><span data-stu-id="c40e1-106">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>
      </webServices>  
     </system.web>
</configuration>  
```  
  
 <span data-ttu-id="c40e1-107">Esto es aconsejable porque WCF requiere mensajes que se ajusten a protocolos diferentes, como SOAP 1,1 y SOAP 1,2, para usar puntos de conexión diferentes.</span><span class="sxs-lookup"><span data-stu-id="c40e1-107">Doing so is advisable because WCF requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="c40e1-108">Si un servicio Web de ASP.NET 2,0 está configurado para admitir SOAP 1,1 y SOAP 1,2, que es la configuración predeterminada, no se puede migrar a un único punto de conexión de WCF en la dirección original que, ciertamente, sería compatible con todos los clientes existentes del servicio Web de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c40e1-108">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single WCF endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="c40e1-109">Además, la elección de SOAP 1.2 en lugar de 1.1, restringirá aún más severamente la clientela del servicio.</span><span class="sxs-lookup"><span data-stu-id="c40e1-109">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="c40e1-110">Desarrollo del servicio</span><span class="sxs-lookup"><span data-stu-id="c40e1-110">Service Development</span></span>  

 <span data-ttu-id="c40e1-111">WCF permite definir contratos de servicio aplicando a las <xref:System.ServiceModel.ServiceContractAttribute> interfaces o a las clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-111">WCF allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="c40e1-112">Se recomienda aplicar el atributo a una interfaz en lugar de a una clase ya que, de este modo, se crea una definición de un contrato que puede ser implementado de manera muy diversa por cualquier número de clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-112">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="c40e1-113">ASP.NET 2.0 admite la opción de aplicar el atributo <xref:System.Web.Services.WebService> a interfaces y a clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-113">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="c40e1-114">Sin embargo, como ya se ha mencionado, existe un defecto en ASP.NET 2.0, por el que el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService> no se activa si se aplica ese atributo a una interfaz en lugar de a una clase.</span><span class="sxs-lookup"><span data-stu-id="c40e1-114">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="c40e1-115">Puesto que suele ser aconsejable modificar el espacio de nombres de un servicio a partir del valor predeterminado, `http://tempuri.org` , mediante el parámetro Namespace del <xref:System.Web.Services.WebService> atributo, uno debe continuar definiendo los servicios Web de ASP.net aplicando el <xref:System.ServiceModel.ServiceContractAttribute> atributo a las interfaces o a las clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-115">Since it is generally advisable to modify the namespace of a service from the default value, `http://tempuri.org`, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
- <span data-ttu-id="c40e1-116">Reduzca el código al mínimo posible en los métodos que definen esas interfaces.</span><span class="sxs-lookup"><span data-stu-id="c40e1-116">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="c40e1-117">Consiga que deleguen su trabajo en otras clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-117">Have them delegate their work to other classes.</span></span> <span data-ttu-id="c40e1-118">Los nuevos tipos de servicio WCF también pueden delegar su trabajo sustancial en esas clases.</span><span class="sxs-lookup"><span data-stu-id="c40e1-118">New WCF service types could then also delegate their substantive work to those classes.</span></span>  
  
- <span data-ttu-id="c40e1-119">Proporcione los nombres explícitos de las operaciones de un servicio mediante el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c40e1-119">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="c40e1-120">Esto es importante, porque los nombres predeterminados para las operaciones en ASP.NET son distintos de los nombres predeterminados proporcionados por WCF.</span><span class="sxs-lookup"><span data-stu-id="c40e1-120">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by WCF.</span></span> <span data-ttu-id="c40e1-121">Al proporcionar nombres explícitos, evita confiar en los predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c40e1-121">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
- <span data-ttu-id="c40e1-122">No implemente operaciones de servicio Web ASP.NET con métodos polimórficos, ya que WCF no admite la implementación de operaciones con métodos polimórficos.</span><span class="sxs-lookup"><span data-stu-id="c40e1-122">Do not implement ASP.NET Web service operations with polymorphic methods, because WCF does not support implementing operations with polymorphic methods.</span></span>  
  
- <span data-ttu-id="c40e1-123">Utilice <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> para proporcionar los valores explícitos de los encabezados HTTP de SOAPAction por los que las solicitudes HTTP se enrutarán a los métodos.</span><span class="sxs-lookup"><span data-stu-id="c40e1-123">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="c40e1-124">Este enfoque evitará tener que basarse en los valores SOAPAction predeterminados usados por ASP.NET y WCF siendo el mismo.</span><span class="sxs-lookup"><span data-stu-id="c40e1-124">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and WCF being the same.</span></span>  
  
- <span data-ttu-id="c40e1-125">Evite la utilización de las extensiones SOAP.</span><span class="sxs-lookup"><span data-stu-id="c40e1-125">Avoid using SOAP extensions.</span></span> <span data-ttu-id="c40e1-126">Si se requieren extensiones SOAP, determine si el propósito para el que se están considerando es una característica ya proporcionada por WCF.</span><span class="sxs-lookup"><span data-stu-id="c40e1-126">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by WCF.</span></span> <span data-ttu-id="c40e1-127">Si es así, considere la posibilidad de no adoptar WCF de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="c40e1-127">If that is indeed the case, then reconsider the choice to not adopt WCF right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="c40e1-128">Administración de estado</span><span class="sxs-lookup"><span data-stu-id="c40e1-128">State Management</span></span>  

 <span data-ttu-id="c40e1-129">Evite tener que mantener el estado de los servicios.</span><span class="sxs-lookup"><span data-stu-id="c40e1-129">Avoid having to maintain state in services.</span></span> <span data-ttu-id="c40e1-130">Mantener el estado no solo tiende a poner en peligro la escalabilidad de una aplicación, pero los mecanismos de administración de estado de ASP.NET y WCF son muy diferentes, aunque WCF admite los mecanismos de ASP.NET en el modo de compatibilidad de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c40e1-130">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and WCF are very different, although WCF does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="c40e1-131">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="c40e1-131">Exception Handling</span></span>  

 <span data-ttu-id="c40e1-132">El diseño de las estructuras de los tipos de datos enviados y recibidos por un servicio, también diseña las estructuras que representan los diferentes tipos de excepciones que pueden producirse en el servicio que se desea hacer llegar a un cliente.</span><span class="sxs-lookup"><span data-stu-id="c40e1-132">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
        get {
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c40e1-133">Otorgue a estas clases la capacidad de serializarse a XML:</span><span class="sxs-lookup"><span data-stu-id="c40e1-133">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 <span data-ttu-id="c40e1-134">De este modo, pueden utilizarse para proporcionar detalles de las instancias <xref:System.Web.Services.Protocols.SoapException> explícitamente iniciadas:</span><span class="sxs-lookup"><span data-stu-id="c40e1-134">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="c40e1-135">Estas clases de excepción se pueden reutilizar fácilmente con la <xref:System.ServiceModel.FaultException%601> clase WCF para iniciar una nueva `FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="c40e1-135">These exception classes will be readily reusable with the WCF <xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="c40e1-136">Seguridad</span><span class="sxs-lookup"><span data-stu-id="c40e1-136">Security</span></span>  

 <span data-ttu-id="c40e1-137">A continuación se indican algunas recomendaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c40e1-137">The following are some security recommendations.</span></span>  
  
- <span data-ttu-id="c40e1-138">Evite el uso de perfiles de ASP.NET 2,0, ya que si se usan, se restringirá el uso del modo de integración de ASP.NET si el servicio se migró a WCF.</span><span class="sxs-lookup"><span data-stu-id="c40e1-138">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to WCF.</span></span>  
  
- <span data-ttu-id="c40e1-139">Evite el uso de ACL para controlar el acceso a los servicios, ya que los servicios Web de ASP.NET admiten las ACL mediante Internet Information Services (IIS), WCF no, ya que los servicios Web de ASP.NET dependen de IIS para el hospedaje, y WCF no tiene que estar hospedado necesariamente en IIS.</span><span class="sxs-lookup"><span data-stu-id="c40e1-139">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), WCF does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
- <span data-ttu-id="c40e1-140">Considere la utilización de los proveedores de funciones de ASP.NET 2.0 para autorizar el acceso a los recursos de un servicio.</span><span class="sxs-lookup"><span data-stu-id="c40e1-140">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c40e1-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="c40e1-141">See also</span></span>

- [<span data-ttu-id="c40e1-142">Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración</span><span class="sxs-lookup"><span data-stu-id="c40e1-142">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](anticipating-adopting-the-wcf-easing-future-integration.md)
