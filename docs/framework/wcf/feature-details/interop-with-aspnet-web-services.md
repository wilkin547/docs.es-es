---
title: "Interoperabilidad con servicios web ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Interoperabilidad con servicios web ASP.NET
La interoperabilidad entre los servicio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y los servicio web de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se puede lograr asegurando que los servicios implementados usen ambas tecnologías de acuerdo con la especificación WS\-I Basic Profile 1.1.Los servicio web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] que cumplen con WS\-I Basic Profile 1.1 son interoperables con clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante el uso de enlace proporcionado por el sistema de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Utilice la opción de [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] de agregar los atributos <xref:System.Web.Services.WebService> y <xref:System.Web.Services.WebMethodAttribute> a una interfaz en lugar de a una clase y escribir una clase para implementar la interfaz, como se muestra en el siguiente código de ejemplo.  
  
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
  
 El uso de esta opción es preferible, porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.  
  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el encabezado HTTP `SOAPAction` para enrutar mensajes.  
  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente.Cuando defina un tipo de datos para su uso con los servicios web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]y en previsión de que se adoptará [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga lo siguiente:  
  
-   Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
-   Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo.No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
-   Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión.Los tipos utilizados en los mensajes por los servicios web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se pueden procesar como contratos de datos a través de aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], lo que produce, entre otras ventajas, un mejor rendimiento en las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services \(IIS\).Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no las admiten.Si es necesario proteger un servicio, utilice las opciones proporcionadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], porque estas opciones son robustas y se basan en protocolos estándar.  
  
## Repercusión en el rendimiento de la carga de ServiceModel HttpModule  
 En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF.Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.  
  
```  
<httpModules>  
    <remove name=”ServiceModel” />  
<httpModules/>  
  
```  
  
## Vea también  
 [Cómo: Configurar servicios WCF para interoperar con clientes de servicios web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)