---
title: Interoperabilidad con servicios web ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 8a0737a36989dd8bc6f5d5670555c7b2218798bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilidad con servicios web ASP.NET
Interoperabilidad entre [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servicios Web y servicios Web de Windows Communication Foundation (WCF) se pueden lograr asegurándose de que los servicios implementados usen ambas tecnologías cumplen con WS-I Basic Profile 1.1 especificación. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Los servicios Web que cumplen con WS-I Basic Profile 1.1 son interoperables con clientes de WCF mediante el enlace proporcionado por el sistema WCF, <xref:System.ServiceModel.BasicHttpBinding>.  
  
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
  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP `SOAPAction`. WCF usa la `SOAPAction` encabezado HTTP para enrutar los mensajes.  
  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para su uso con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]servicios Web de prever la adopción de WCF, realice lo siguiente:  
  
-   Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
-   Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
-   Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos utilizados en los mensajes por [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] servicios Web pueden ser procesados como contratos de datos por las aplicaciones de WCF, lo que produce, entre otras ventajas, un mejor rendimiento en aplicaciones de WCF.  
  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes de WCF no las admiten. Si un servicio debe estar protegido, utilice las opciones proporcionadas por WCF, ya que estas opciones son robustas y se basan en protocolos estándares.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Repercusión en el rendimiento de la carga de ServiceModel HttpModule  
 En .NET Framework 3.0, se instaló el `HttpModule` de WCF en el archivo raíz Web.config, de modo que cada aplicación ASP.NET sea compatible con WCF. Esto puede afectar al rendimiento, por lo que es posible quitar `ServiceModel` del archivo Web.config, como se muestra en el siguiente ejemplo.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Vea también  
 [Configuración de servicios WCF para interoperar con clientes de servicios web ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
