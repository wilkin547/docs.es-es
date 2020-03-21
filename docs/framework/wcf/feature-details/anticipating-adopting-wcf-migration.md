---
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185469"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración
Para garantizar una migración futura más fácil de nuevas aplicaciones de ASP.NET a WCF, siga las recomendaciones anteriores, así como las siguientes recomendaciones.  
  
## <a name="protocols"></a>Protocolos  
 Deshabilite la compatibilidad de ASP.NET 2.0 para SOAP 1.2:  
  
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
  
 Hacerlo es recomendable porque WCF requiere mensajes que se ajustan a diferentes protocolos, como SOAP 1.1 y SOAP 1.2, para ir mediante el uso de diferentes extremos. Si un servicio Web ASP.NET 2.0 está configurado para admitir SOAP 1.1 y SOAP 1.2, que es la configuración predeterminada, no se puede migrar a un único extremo WCF en la dirección original que sería ciertamente compatible con todos los ASP.NET Web clientes existentes del servicio. Además, la elección de SOAP 1.2 en lugar de 1.1, restringirá aún más severamente la clientela del servicio.  
  
## <a name="service-development"></a>Desarrollo del servicio  
 WCF permite definir contratos de servicio <xref:System.ServiceModel.ServiceContractAttribute> aplicando el ya sea a interfaces o a clases. Se recomienda aplicar el atributo a una interfaz en lugar de a una clase ya que, de este modo, se crea una definición de un contrato que puede ser implementado de manera muy diversa por cualquier número de clases. ASP.NET 2.0 admite la opción de aplicar el atributo <xref:System.Web.Services.WebService> a interfaces y a clases. Sin embargo, como ya se ha mencionado, existe un defecto en ASP.NET 2.0, por el que el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService> no se activa si se aplica ese atributo a una interfaz en lugar de a una clase. Puesto que generalmente es recomendable modificar el espacio de `http://tempuri.org`nombres de un <xref:System.Web.Services.WebService> servicio desde el valor predeterminado, mediante el <xref:System.ServiceModel.ServiceContractAttribute> parámetro Namespace del atributo, se debe seguir definiendo ASP.NET Web Services aplicando el atributo a interfaces o a clases.  
  
- Reduzca el código al mínimo posible en los métodos que definen esas interfaces. Consiga que deleguen su trabajo en otras clases. Los nuevos tipos de servicio WCF también podrían delegar su trabajo sustantivo en esas clases.  
  
- Proporcione los nombres explícitos de las operaciones de un servicio mediante el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Hacerlo es importante, porque los nombres predeterminados para las operaciones en ASP.NET son diferentes de los nombres predeterminados proporcionados por WCF. Al proporcionar nombres explícitos, evita confiar en los predeterminados.  
  
- No implemente operaciones de servicio web ASP.NET con métodos polimórficos, porque WCF no admite la implementación de operaciones con métodos polimórficos.  
  
- Utilice <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> para proporcionar los valores explícitos de los encabezados HTTP de SOAPAction por los que las solicitudes HTTP se enrutarán a los métodos.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Tomar este enfoque evitará tener que depender de los valores SOAPAction predeterminados utilizados por ASP.NET y WCF es el mismo.  
  
- Evite la utilización de las extensiones SOAP. Si se requieren extensiones SOAP, determine si el propósito para el que se están considerando es una característica que ya proporciona WCF. Si ese es realmente el caso, a continuación, reconsiderar la opción de no adoptar WCF de inmediato.  
  
## <a name="state-management"></a>Administración de estado  
 Evite tener que mantener el estado de los servicios. No solo el mantenimiento del estado tiende a comprometer la escalabilidad de una aplicación, sino que los mecanismos de administración de estado de ASP.NET y WCF son muy diferentes, aunque WCF admite los mecanismos de ASP.NET en ASP.NET modo de compatibilidad.  
  
## <a name="exception-handling"></a>Control de excepciones.  
 El diseño de las estructuras de los tipos de datos enviados y recibidos por un servicio, también diseña las estructuras que representan los diferentes tipos de excepciones que pueden producirse en el servicio que se desea hacer llegar a un cliente.  
  
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
  
 Otorgue a estas clases la capacidad de serializarse a XML:  
  
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
  
 De este modo, pueden utilizarse para proporcionar detalles de las instancias <xref:System.Web.Services.Protocols.SoapException> explícitamente iniciadas:  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Estas clases de excepción serán <xref:System.ServiceModel.FaultException%601> fácilmente reutilizables con la clase WCF para lanzar un nuevo`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Seguridad  
 A continuación se indican algunas recomendaciones de seguridad.  
  
- Evite usar ASP.NET 2.0 Profiles, ya que su uso restringiría el uso de ASP.NET modo de integración si el servicio se migró a WCF.  
  
- Evite usar ACL para controlar el acceso a los servicios, ya que ASP.NET servicios web admite ACL mediante Internet Information Services (IIS), WCF no, porque ASP.NET servicios web dependen de IIS para hospedarse y WCF no necesariamente tiene que hospedarse en IIS.  
  
- Considere la utilización de los proveedores de funciones de ASP.NET 2.0 para autorizar el acceso a los recursos de un servicio.  
  
## <a name="see-also"></a>Consulte también

- [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
