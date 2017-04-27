---
title: "Creaci&#243;n de servicios interoperables de WS-I Basic Profile 1.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "configuración [WCF], servicios interoperables"
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Creaci&#243;n de servicios interoperables de WS-I Basic Profile 1.1
Para configurar un extremo del servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para ser interoperable con clientes de servicios Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]:  
  
-   Utilice la <xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName> que el tipo de enlace para el extremo de servicio.  
  
-   No utilice devolución de llamada sino características de contrato de sesión o comportamientos de transacción en su punto de conexión de servicio  
  
 Puede habilitar opcionalmente el soporte para HTTPS y la autenticación del cliente del nivel de transporte en el enlace.  
  
 Las siguientes características de la <xref:System.ServiceModel.BasicHttpBinding> clase requieren la funcionalidad más allá de WS-I Basic Profile 1.1:  
  
-   Codificación de mensajes de Message Transmission Optimization Mechanism (MTOM) controlada por la <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=fullName> propiedad. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.WSMessageEncoding?displayProperty=fullName> para no utilizar MTOM.  
  
-   Modo de seguridad que controla el <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=fullName> valor proporciona compatibilidad con WS-Security conforme con WS-I Basic Security Profile 1.0. Deje esta propiedad en su valor predeterminado, que es <xref:System.ServiceModel.SecurityMode?displayProperty=fullName> no usar WS-Security.  
  
 Para hacer que los metadatos de un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio disponible para [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], utilice las herramientas de generación de cliente de servicio Web: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/es-es/b9210348-8bc2-4367-8c91-d1a04b403e88), [herramienta descubrimiento de servicios Web (Disco.exe)](http://msdn.microsoft.com/es-es/acd88078-c581-42bc-94ca-6633e2851979)y el `Add Web Reference` característica [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]; debe habilitar la publicación de metadatos. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Extremos de metadatos de publicación](../../../docs/framework/wcf/publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 El código de ejemplo siguiente muestra cómo agregar un extremo [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que es compatible con clientes de servicios Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] en código y, alternativamente, en archivos de configuración.  
  
### <a name="code"></a>Código  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
  
 <!-- TODO: review snippet reference [!code[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/common/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  -->  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad con servicios Web de ASP.NET](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)