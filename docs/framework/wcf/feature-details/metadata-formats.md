---
title: Formatos de metadatos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ee7376f87fd0e4ce15d192dd53f872e84187acc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-formats"></a>Formatos de metadatos
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] admite los formatos de metadatos que se encuentran en la siguiente tabla.  
  
## <a name="metadata-specifications-and-usage"></a>Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el lenguaje de descripción de servicios Web (WSDL) para describir servicios.|  
|esquema XML|[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) y [esquema XML parte 1: estructuras, segunda edición](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza el esquema XML para describir los tipos de datos utilizados en los mensajes.|  
|Directiva WS|[Directiva de servicios Web 1.2 - Framework (WS-Policy)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Directiva de servicios Web 1.5 - Framework](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la especificación WS-Policy 1.2 ó 1.5 con las aserciones específicas del dominio para describir requisitos y funciones del servicio.|  
|Datos adjuntos de directivas WS|[Directiva de servicios Web 1.2: datos adjuntos (WS-PolicyAttachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa Datos adjuntos de directivas WS para adjuntar expresiones de directivas en varios ámbitos de WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de servicios Web (WS-MetadataExchange) versión 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0 - enlace WSDL](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-Addressing Binding para que WSDL adjunte información del direccionamiento en WSDL.|  
  
## <a name="see-also"></a>Vea también  
 [Protocolos admitidos por los enlaces de interoperabilidad proporcionados por el sistema de servicios Web](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL y directiva](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
