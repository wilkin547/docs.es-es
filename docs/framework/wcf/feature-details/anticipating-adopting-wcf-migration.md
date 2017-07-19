---
title: "Anticipaci&#243;n de la adopci&#243;n de Windows Communication Foundation: c&#243;mo facilitar la futura migraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Anticipaci&#243;n de la adopci&#243;n de Windows Communication Foundation: c&#243;mo facilitar la futura migraci&#243;n
Para garantizar una migración futura más fácil de nuevas aplicaciones ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], siga las recomendaciones anteriores y las siguientes.  
  
## Protocolos  
 Deshabilite la compatibilidad de ASP.NET 2.0 para SOAP 1.2:  
  
```  
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
  
 Esto es aconsejable ya que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exige que los mensajes sean conformes a protocolos diferentes, como SOAP 1.1 y SOAP 1.2, para poder utilizar distintos extremos.  Si un servicio web de ASP.NET 2.0 se configura para admitir SOAP 1.1 y SOAP 1.2, que es la configuración predeterminada, no se puede migrar hacia un único extremo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en la dirección original que, por supuesto, sería compatible con todos los clientes existentes del servicio web ASP.NET.  Además, la elección de SOAP 1.2 en lugar de 1.1, restringirá aún más severamente la clientela del servicio.  
  
## Desarrollo del servicio  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite definir los contratos de servicios aplicando <xref:System.ServiceModel.ServiceContractAttribute> a las interfaces o a las clases.  Se recomienda aplicar el atributo a una interfaz en lugar de a una clase ya que, de este modo, se crea una definición de un contrato que puede ser implementado de manera muy diversa por cualquier número de clases.  ASP.NET 2.0 admite la opción de aplicar el atributo <xref:System.Web.Services.WebService> a interfaces y a clases.  Sin embargo, como ya se ha mencionado, existe un defecto en ASP.NET 2.0, por el que el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService> no se activa si se aplica ese atributo a una interfaz en lugar de a una clase.  Dado que en general resulta aconsejable modificar el valor predeterminado del espacio de nombres de un servicio, http:\/\/tempuri.org, utilizando el parámetro de espacio de nombres del atributo <xref:System.Web.Services.WebService>, los servicios web ASP.NET deberían seguir definiéndose mediante la aplicación del atributo <xref:System.ServiceModel.ServiceContractAttribute> a las interfaces o a las clases.  
  
-   Reduzca el código al mínimo posible en los métodos que definen esas interfaces.  Consiga que deleguen su trabajo en otras clases.  Así, los nuevos tipos de servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también podrán delegar su trabajo principal a esas clases.  
  
-   Proporcione los nombres explícitos de las operaciones de un servicio mediante el parámetro `MessageName` de <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Esto es importante porque los nombres predeterminados de las operaciones en ASP.NET son diferentes de los nombres predeterminados proporcionados por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Al proporcionar nombres explícitos, evita confiar en los predeterminados.  
  
-   No implemente las operaciones del servicio web ASP.NET con métodos polimórficos, ya que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no es compatible con la utilización de estos métodos para la implementación de operaciones.  
  
-   Utilice <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> para proporcionar los valores explícitos de los encabezados HTTP de SOAPAction por los que las solicitudes HTTP se enrutarán a los métodos.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Al adoptar este enfoque, evitará tener que confiar en los valores SOAPAction predeterminados utilizados por ASP.NET y que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sea igual.  
  
-   Evite la utilización de las extensiones SOAP.  En caso de que se requieran extensiones SOAP, determine si el propósito para el que se están considerando es una característica que ya le proporciona [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Si así es, reconsidere la opción de no adoptar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] inmediatamente.  
  
## Administración de estado  
 Evite tener que mantener el estado de los servicios.  El mantenimiento del estado no solo tiende a poner en peligro la escalabilidad de una aplicación, además los mecanismos de administración de estados de ASP.NET e [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son muy diferentes, a pesar de que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite los mecanismos de ASP.NET en el modo de compatibilidad de ASP.NET.  
  
## Control de excepciones  
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
  
 Estas clases de excepción pronto podrán reutilizarse con la clase [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] <xref:System.ServiceModel.FaultException%601> para iniciar una nueva `FaultException<AnticipatedException>(anticipatedException);`  
  
## Seguridad  
 A continuación se indican algunas recomendaciones de seguridad.  
  
-   Evite utilizar perfiles de ASP.NET 2.0, ya que su uso restringiría la utilización del modo de integración de ASP.NET si el servicio migró a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Evite utilizar las ACL para controlar el acceso a los servicios, si bien es cierto que los servicios web ASP.NET son compatibles con las ACL que utilizan Internet Information Services \(IIS\), no es el caso de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], los servicios web ASP.NET dependen de IIS para su hospedaje, y WCF no tiene que estar necesariamente hospedado en IIS.  
  
-   Considere la utilización de los proveedores de funciones de ASP.NET 2.0 para autorizar el acceso a los recursos de un servicio.  
  
## Vea también  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)