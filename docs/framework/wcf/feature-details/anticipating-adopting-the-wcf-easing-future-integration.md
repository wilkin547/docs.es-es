---
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: c6e749c32947a4159d6bfd56c4d30a06f6ef0b7f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316341"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración
Si utiliza ASP.NET hoy en día y prevé usar WCF en el futuro, este tema proporcionan instrucciones para asegurarse de que los nuevos servicios Web ASP.NET funcionarán bien junto con las aplicaciones WCF.  
  
## <a name="general-recommendations"></a>Recomendaciones generales  
 Adopte ASP.NET 2.0 para cualquier nuevo servicio. Al hacer esto, se proporcionará acceso a las mejoras y ampliaciones de la nueva versión. Sin embargo, también permitirá la posibilidad de utilizar los componentes de ASP.NET 2.0 junto con los componentes WCF en la misma aplicación.  
  
## <a name="protocols"></a>Protocolos  
 Use la nueva facilidad de ASP.NET 2.0 para validar la conformidad con WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Servicios Web ASP.NET que cumplen con WS-I Basic Profile 1.1 serán interoperable con clientes de WCF mediante el uso de enlace, WCF predefinido <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Desarrollo del servicio  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP SOAPAction. WCF usa el encabezado HTTP SOAPAction para enrutar los mensajes.  
  
## <a name="data-representation"></a>Representación de datos  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para su uso con los servicios Web ASP.NET en previsión de adoptar WCF en el futuro, realice lo siguiente:  
  
1. Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
2. Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
 Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos utilizados en los mensajes de servicios Web ASP.NET podrán ser procesados como contratos de datos por aplicaciones de WCF, proporcionando, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.  
  
## <a name="security"></a>Seguridad  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes de WCF no las admiten. Si es necesario proteger un servicio, utilice las opciones proporcionadas por WCF, ya que estas opciones son mejores y se basan en protocolos estándares.  
  
## <a name="see-also"></a>Vea también

- [Anticipación de la adopción de Windows Communication Foundation: Cómo facilitar la futura migración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
