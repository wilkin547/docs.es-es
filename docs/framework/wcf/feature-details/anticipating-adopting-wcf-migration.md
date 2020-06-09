---
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: b43f509bd49ebe89d7ed0be4c37b3ed179aaeb8c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576504"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración
Para garantizar una migración futura más sencilla de las nuevas aplicaciones de ASP.NET a WCF, siga las recomendaciones anteriores, así como las recomendaciones siguientes.  
  
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
  
 Esto es aconsejable porque WCF requiere mensajes que se ajusten a protocolos diferentes, como SOAP 1,1 y SOAP 1,2, para usar puntos de conexión diferentes. Si un servicio Web de ASP.NET 2,0 está configurado para admitir SOAP 1,1 y SOAP 1,2, que es la configuración predeterminada, no se puede migrar a un único punto de conexión de WCF en la dirección original que, ciertamente, sería compatible con todos los clientes existentes del servicio Web de ASP.NET. Además, la elección de SOAP 1.2 en lugar de 1.1, restringirá aún más severamente la clientela del servicio.  
  
## <a name="service-development"></a>Desarrollo del servicio  
 WCF permite definir contratos de servicio aplicando a las <xref:System.ServiceModel.ServiceContractAttribute> interfaces o a las clases. Se recomienda aplicar el atributo a una interfaz en lugar de a una clase ya que, de este modo, se crea una definición de un contrato que puede ser implementado de manera muy diversa por cualquier número de clases. ASP.NET 2.0 admite la opción de aplicar el atributo <xref:System.Web.Services.WebService> a interfaces y a clases. Sin embargo, como ya se ha mencionado, existe un defecto en ASP.NET 2.0, por el que el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService> no se activa si se aplica ese atributo a una interfaz en lugar de a una clase. Puesto que suele ser aconsejable modificar el espacio de nombres de un servicio a partir del valor predeterminado, `http://tempuri.org` , mediante el parámetro Namespace del <xref:System.Web.Services.WebService> atributo, uno debe continuar definiendo los servicios Web de ASP.net aplicando el <xref:System.ServiceModel.ServiceContractAttribute> atributo a las interfaces o a las clases.  
  
- Reduzca el código al mínimo posible en los métodos que definen esas interfaces. Consiga que deleguen su trabajo en otras clases. Los nuevos tipos de servicio WCF también pueden delegar su trabajo sustancial en esas clases.  
  
- Proporcione los nombres explícitos de las operaciones de un servicio mediante el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Esto es importante, porque los nombres predeterminados para las operaciones en ASP.NET son distintos de los nombres predeterminados proporcionados por WCF. Al proporcionar nombres explícitos, evita confiar en los predeterminados.  
  
- No implemente operaciones de servicio Web ASP.NET con métodos polimórficos, ya que WCF no admite la implementación de operaciones con métodos polimórficos.  
  
- Utilice <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> para proporcionar los valores explícitos de los encabezados HTTP de SOAPAction por los que las solicitudes HTTP se enrutarán a los métodos.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Este enfoque evitará tener que basarse en los valores SOAPAction predeterminados usados por ASP.NET y WCF siendo el mismo.  
  
- Evite la utilización de las extensiones SOAP. Si se requieren extensiones SOAP, determine si el propósito para el que se están considerando es una característica ya proporcionada por WCF. Si es así, considere la posibilidad de no adoptar WCF de forma inmediata.  
  
## <a name="state-management"></a>Administración de estado  
 Evite tener que mantener el estado de los servicios. Mantener el estado no solo tiende a poner en peligro la escalabilidad de una aplicación, pero los mecanismos de administración de estado de ASP.NET y WCF son muy diferentes, aunque WCF admite los mecanismos de ASP.NET en el modo de compatibilidad de ASP.NET.  
  
## <a name="exception-handling"></a>Control de excepciones  
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
  
 Estas clases de excepción se pueden reutilizar fácilmente con la <xref:System.ServiceModel.FaultException%601> clase WCF para iniciar una nueva`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Seguridad  
 A continuación se indican algunas recomendaciones de seguridad.  
  
- Evite el uso de perfiles de ASP.NET 2,0, ya que si se usan, se restringirá el uso del modo de integración de ASP.NET si el servicio se migró a WCF.  
  
- Evite el uso de ACL para controlar el acceso a los servicios, ya que los servicios Web de ASP.NET admiten las ACL mediante Internet Information Services (IIS), WCF no, ya que los servicios Web de ASP.NET dependen de IIS para el hospedaje, y WCF no tiene que estar hospedado necesariamente en IIS.  
  
- Considere la utilización de los proveedores de funciones de ASP.NET 2.0 para autorizar el acceso a los recursos de un servicio.  
  
## <a name="see-also"></a>Vea también

- [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](anticipating-adopting-the-wcf-easing-future-integration.md)
