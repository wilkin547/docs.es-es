---
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 171a31b375eae4c032849c2a1c2090f5d9ff856f
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48580646"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración
Para garantizar una migración futura más sencilla de nuevas aplicaciones de ASP.NET a WCF, siga las recomendaciones anteriores, así como las siguientes recomendaciones.  
  
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
  
 Si lo hace, es aconsejable porque WCF requiere que los mensajes conforme a protocolos diferentes, como SOAP 1.1 y SOAP 1.2, vaya con extremos diferentes. Si un servicio está configurado para admitir SOAP 1.1 y SOAP 1.2, que es la configuración predeterminada, a continuación, no puede ser de Web de ASP.NET 2.0 se migrado avance a un único extremo WCF en la dirección original que sería ciertamente sea compatible con toda la Web de ASP.NET clientes existentes del servicio. Además, la elección de SOAP 1.2 en lugar de 1.1, restringirá aún más severamente la clientela del servicio.  
  
## <a name="service-development"></a>Desarrollo del servicio  
 WCF permite definir los contratos de servicios aplicando el <xref:System.ServiceModel.ServiceContractAttribute> a las interfaces o clases. Se recomienda aplicar el atributo a una interfaz en lugar de a una clase ya que, de este modo, se crea una definición de un contrato que puede ser implementado de manera muy diversa por cualquier número de clases. ASP.NET 2.0 admite la opción de aplicar el atributo <xref:System.Web.Services.WebService> a interfaces y a clases. Sin embargo, como ya se ha mencionado, existe un defecto en ASP.NET 2.0, por el que el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService> no se activa si se aplica ese atributo a una interfaz en lugar de a una clase. Puesto que es aconsejable modificar el espacio de nombres de un servicio desde el valor predeterminado, `http://tempuri.org`, mediante el parámetro Namespace de la <xref:System.Web.Services.WebService> atributo, deberían seguir definiéndose servicios Web de ASP.NET aplicando el <xref:System.ServiceModel.ServiceContractAttribute> atributo de interfaces o clases.  
  
-   Reduzca el código al mínimo posible en los métodos que definen esas interfaces. Consiga que deleguen su trabajo en otras clases. Nuevos tipos de servicio WCF, a continuación, también podrían delegar su trabajo principal a esas clases.  
  
-   Proporcione los nombres explícitos de las operaciones de un servicio mediante el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Si lo hace, es importante, porque los nombres predeterminados para las operaciones en ASP.NET son diferentes de los nombres predeterminados proporcionados por WCF. Al proporcionar nombres explícitos, evita confiar en los predeterminados.  
  
-   No implementa las operaciones del servicio Web de ASP.NET con métodos polimórficos, porque WCF no admite la implementación de operaciones con métodos polimórficos.  
  
-   Utilice <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> para proporcionar los valores explícitos de los encabezados HTTP de SOAPAction por los que las solicitudes HTTP se enrutarán a los métodos.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Este enfoque, evitará tener que confiar en el valor predeterminado de los valores SOAPAction utilizados por ASP.NET y WCF, que es el mismo.  
  
-   Evite la utilización de las extensiones SOAP. Si se requieren las extensiones SOAP, a continuación, determine si el propósito para el que se están considerando es una característica que se haya proporcionado por WCF. Si ese es realmente el caso, reconsidere la opción para no adoptar WCF de inmediato.  
  
## <a name="state-management"></a>Administración de estado  
 Evite tener que mantener el estado de los servicios. No sólo mantener el estado tiende a poner en peligro la escalabilidad de una aplicación, pero los mecanismos de administración de estado de ASP.NET y WCF son muy diferentes, aunque WCF es compatible con los mecanismos ASP.NET en modo de compatibilidad ASP.NET.  
  
## <a name="exception-handling"></a>Control de excepciones  
 El diseño de las estructuras de los tipos de datos enviados y recibidos por un servicio, también diseña las estructuras que representan los diferentes tipos de excepciones que pueden producirse en el servicio que se desea hacer llegar a un cliente.  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
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
  
```  
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
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Estas clases de excepción pronto podrán reutilizarse con WCF<xref:System.ServiceModel.FaultException%601> clase para iniciar una nueva `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Seguridad  
 A continuación se indican algunas recomendaciones de seguridad.  
  
-   Evitar el uso de perfiles de ASP.NET 2.0, ya que su uso restringiría la utilización del modo de integración de ASP.NET si se migró el servicio WCF.  
  
-   Evite el uso de ACL para controlar el acceso a los servicios, como ASP.NET Web services es compatible con las ACL que utilizan Internet Information Services (IIS), WCF no es así, porque los servicios Web ASP.NET dependen de IIS para hospedar y WCF no necesariamente deben hospedarse en IIS.  
  
-   Considere la utilización de los proveedores de funciones de ASP.NET 2.0 para autorizar el acceso a los recursos de un servicio.  
  
## <a name="see-also"></a>Vea también  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
