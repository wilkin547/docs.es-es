---
description: 'Más información acerca de cómo anticiparse a la adopción del Windows Communication Foundation: facilitar la futura integración'
title: 'Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: 512e35e8a4cd6057c96e96a1474f393c3f006525
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643883"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración

Si usa ASP.NET hoy y prevé usar WCF en el futuro, en este tema se proporcionan instrucciones para asegurarse de que los nuevos servicios Web de ASP.NET funcionarán bien junto con las aplicaciones WCF.  
  
## <a name="general-recommendations"></a>Recomendaciones generales  

 Adopte ASP.NET 2.0 para cualquier nuevo servicio. Al hacer esto, se proporcionará acceso a las mejoras y ampliaciones de la nueva versión. Sin embargo, también permitirá la posibilidad de usar componentes de ASP.NET 2,0 junto con componentes de WCF en la misma aplicación.  
  
## <a name="protocols"></a>Protocolos  

 Use la nueva facilidad de ASP.NET 2.0 para validar la conformidad con WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Los servicios Web de ASP.NET que cumplen con WS-I Basic Profile 1,1 serán interoperables con los clientes de WCF mediante el enlace predefinido de WCF <xref:System.ServiceModel.BasicHttpBinding> .  
  
## <a name="service-development"></a>Desarrollo del servicio  

 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP SOAPAction. WCF usa el encabezado HTTP SOAPAction para enrutar mensajes.  
  
## <a name="data-representation"></a>Representación de datos  

 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para su uso con los servicios Web de ASP.NET en previsión de adoptar WCF en el futuro, haga lo siguiente:  
  
1. Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
2. Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
 Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos que se usan en los mensajes de los servicios Web de ASP.NET se podrán procesar como contratos de datos por parte de las aplicaciones WCF, produciendo, entre otras ventajas, un mejor rendimiento en las aplicaciones WCF.  
  
## <a name="security"></a>Seguridad  

 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes de WCF no las admiten. Si es necesario proteger un servicio, utilice las opciones proporcionadas por WCF, ya que estas opciones son más enriquecidas y se basan en protocolos estándar.  
  
## <a name="see-also"></a>Vea también

- [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración](anticipating-adopting-wcf-migration.md)
