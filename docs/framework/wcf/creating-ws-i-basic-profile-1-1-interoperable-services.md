---
title: Creación de servicios interoperables de WS-I Basic Profile 1.1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd08dca74ddb3f77e37a3aa4d67cf6d495bf5d16
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Creación de servicios interoperables de WS-I Basic Profile 1.1
Para configurar un extremo del servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para ser interoperable con clientes de servicios Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]:  
  
-   Utilice el tipo <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> como tipo de enlace para su extremo de servicio.  
  
-   No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su punto de conexión de servicio  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.  
  
 Las características siguientes de la clase <xref:System.ServiceModel.BasicHttpBinding> requieren la funcionalidad más allá de WS-I Basic Profile 1.1:  
  
-   Codificación de mensajes del Mecanismo de optimización de transmisión del mensajes (MTOM) controlada por la propiedad <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> para no utilizar MTOM.  
  
-   La seguridad de mensaje que controla el valor <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> proporciona compatibilidad con WS-Security conforme a WS-I Basic Security Profile 1.0. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType>, para no usar WS-Security.  
  
 Para que los metadatos una [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio disponible para [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use las herramientas de generación de cliente de servicio Web: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(Web Services Discovery Tool Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)y el `Add Web Reference` característica en Visual Studio; también debe habilitar la publicación de metadatos. Para obtener más información, consulte [publicación de extremos de metadatos](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Ejemplo de código siguiente muestra cómo agregar un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] punto de conexión que es compatible con [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] clientes de servicios en código y, o bien, en un archivo de configuración Web.  
  
### <a name="code"></a>Código  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad con servicios web ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
