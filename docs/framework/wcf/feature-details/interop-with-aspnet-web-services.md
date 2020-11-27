---
title: Interoperabilidad con servicios web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: cca4e1b3da26d8026d41d0a7107432cdd2960545
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276638"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilidad con servicios web ASP.NET

La interoperabilidad entre los servicios Web de ASP.NET y los servicios Web de Windows Communication Foundation (WCF) se puede lograr asegurándose de que los servicios implementados mediante ambas tecnologías se ajusten a la especificación de WS-I Basic Profile 1,1. Los servicios Web de ASP.NET que cumplen con WS-I Basic Profile 1,1 son interoperables con los clientes de WCF mediante el enlace proporcionado por el sistema WCF, <xref:System.ServiceModel.BasicHttpBinding> .  
  
 Use la opción ASP.NET 2,0 de agregar <xref:System.Web.Services.WebService> los <xref:System.Web.Services.WebMethodAttribute> atributos y a una interfaz en lugar de a una clase, y escriba una clase para implementar la interfaz, tal como se muestra en el código de ejemplo siguiente.  
  
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
  
 El uso de esta opción es preferible, porque la interfaz con el atributo <xref:System.Web.Services.WebService> constituye un contrato para las operaciones realizadas por el servicio, que puede reutilizarse con diferentes clases que podrían implementar ese mismo contrato de distintas maneras.  
  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`. WCF usa el `SOAPAction` encabezado HTTP para enrutar los mensajes.  
  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para su uso con ASP. NETWeb Services en previsión de adoptar WCF, haga lo siguiente:  
  
- Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
- Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
- Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos que se usan en los mensajes de los servicios Web ASP.NET pueden procesarse como contratos de datos por parte de las aplicaciones WCF, produciendo, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.  
  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes de WCF no las admiten. Si se debe proteger un servicio, utilice las opciones proporcionadas por WCF, ya que estas opciones son sólidas y se basan en protocolos estándar.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Repercusión en el rendimiento de la carga de ServiceModel HttpModule  

 En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF. Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para configurar servicios WCF para interoperar con clientes de servicios web ASP.NET](config-wcf-service-with-aspnet-web-service.md)
