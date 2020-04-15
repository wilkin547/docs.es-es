---
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: fd7828cccb1a19a17e899525d863021d3670fbdd
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389760"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Creación de servicios interoperables de WS-I Basic Profile 1.1
Para configurar un extremo de servicio WCF para que sea interoperable con ASP.NET clientes de servicio Web:  
  
- Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su extremo de servicio.  
  
- No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su extremo de servicio  
  
Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.  
  
Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:  
  
- Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.  
  
- La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.  
  
Para que los metadatos de un servicio WCF estén disponibles para ASP.NET, use las herramientas de generación de cliente de servicio web: Herramienta de lenguaje de descripción de [servicios web (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29)Herramienta de detección de [servicios web (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)y la característica **Agregar referencia web** en Visual Studio. Habilite la publicación de metadatos. Para obtener más información, consulte Publicación de [extremos](publishing-metadata-endpoints.md)de metadatos .  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 En el código de ejemplo siguiente se muestra cómo agregar un extremo WCF que es compatible con ASP.NET clientes de servicio Web en código y, alternativamente, en un archivo de configuración.  
  
### <a name="code"></a>Código  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Consulte también

- [Interoperabilidad con servicios web ASP.NET](./feature-details/interop-with-aspnet-web-services.md)
