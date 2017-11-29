---
title: "Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f60b2566895acfd7d2b749729fab9c3f5deb20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración
Si utiliza ASP.NET hoy, y prevé que utilizará [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el futuro, este tema proporciona la orientación para garantizar que los nuevos servicios web ASP.NET funcionarán bien junto con las aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="general-recommendations"></a>Recomendaciones generales  
 Adopte ASP.NET 2.0 para cualquier nuevo servicio. Al hacer esto, se proporcionará acceso a las mejoras y ampliaciones de la nueva versión. Sin embargo, también permitirá la posibilidad de utilizar los componentes de ASP.NET 2.0 junto con los componentes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en la misma aplicación.  
  
## <a name="protocols"></a>Protocolos  
 Use la nueva facilidad de ASP.NET 2.0 para validar la conformidad con WS-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Los servicios web ASP.NET que cumplen con WS-I Basic Profile 1.1 serán interoperables con clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando el enlace predefinido de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.ServiceModel.BasicHttpBinding>.  
  
## <a name="service-development"></a>Desarrollo del servicio  
 Evite usar el atributo <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> para que los mensajes se enruten a métodos en función del nombre completo del elemento de cuerpo del mensaje SOAP en lugar del encabezado HTTP SOAPAction. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el encabezado HTTP SOAPAction para enrutar mensajes.  
  
## <a name="data-representation"></a>Representación de datos  
 El XML en el que <xref:System.Xml.Serialization.XmlSerializer> serializa de forma predeterminada un tipo es semánticamente idéntico al XML en el que <xref:System.Runtime.Serialization.DataContractSerializer> serializa un tipo, dando por hecho que el espacio de nombres para el XML se define explícitamente. Al definir un tipo de datos para el uso con servicios web ASP.NET al prever la adopción en el futuro de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], haga lo siguiente:  
  
1.  Defina el tipo mediante las clases de .NET Framework en lugar de mediante el Esquema XML.  
  
2.  Agregue solo <xref:System.SerializableAttribute> y <xref:System.Xml.Serialization.XmlRootAttribute> a la clase, utilizando el último para definir explícitamente el espacio de nombres del tipo. No agregue atributos adicionales del espacio de nombres <xref:System.Xml.Serialization> para controlar cómo se traducirá la clase de .NET Framework a XML.  
  
 Mediante el uso de este enfoque, debería ser capaz de convertir más adelante las clases .NET en contratos de datos agregando  <xref:System.Runtime.Serialization.DataContractAttribute> y <xref:System.Runtime.Serialization.DataMemberAttribute> sin modificar significativamente el XML en el que las clases se serializan para la transmisión. Los tipos utilizados en mensajes por los servicios web ASP.NET podrán ser procesados como contratos de datos mediante aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], proporcionando, entre otras ventajas, un mejor rendimiento en aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="security"></a>Seguridad  
 Evite usar las opciones de autenticación proporcionadas por Internet Information Services (IIS). Los clientes de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no las admiten. Si es necesario proteger un servicio, utilice las opciones proporcionadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], porque estas opciones son mejores y se basan en protocolos estándar.  
  
## <a name="see-also"></a>Vea también  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
