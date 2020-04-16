---
title: Interoperabilidad con servicios web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 41810d8044e4b7ff3193950a914edbf1e61cffb1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464091"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilidad con servicios web ASP.NET
La interoperabilidad entre los servicios web de ASP.NET y los servicios web de Windows Communication Foundation (WCF) se puede lograr garantizando que los servicios implementados mediante ambas tecnologías se ajustan a la especificación WS-I Basic Profile 1.1. ASP.NET servicios web que se ajustan al perfil básico 1.1 de WS-I son <xref:System.ServiceModel.BasicHttpBinding>interoperables con los clientes WCF mediante el enlace proporcionado por el sistema WCF, .  
  
 Utilice ASP.NET opción 2.0 <xref:System.Web.Services.WebService> <xref:System.Web.Services.WebMethodAttribute> de agregar los atributos y a una interfaz en lugar de a una clase y escribir una clase para implementar la interfaz, como se muestra en el siguiente código de ejemplo.  
  
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
  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`. WCF usa `SOAPAction` el encabezado HTTP para enrutar mensajes.  
  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para su uso con servicios ASP.NETWeb en previsión de adoptar WCF, haga lo siguiente:  
  
- Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
- Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
- Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos utilizados en los mensajes por ASP.NET servicios Web se pueden procesar como contratos de datos por las aplicaciones WCF, lo que produce, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.  
  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes WCF no los admiten. Si se debe proteger un servicio, use las opciones proporcionadas por WCF, porque estas opciones son sólidas y se basan en protocolos estándar.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Repercusión en el rendimiento de la carga de ServiceModel HttpModule  
 En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF. Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para configurar servicios WCF para interoperar con clientes de servicios web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
