---
title: Formatos de metadatos
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: a3c6b1f551d1bff8c68a91f33e62df289d2078cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33493443"
---
# <a name="metadata-formats"></a>Formatos de metadatos
Windows Communication Foundation (WCF) es compatible con los formatos de metadatos en la tabla siguiente.  
  
## <a name="metadata-specifications-and-usage"></a>Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web (WSDL) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF usa el lenguaje de descripción de servicios Web (WSDL) para describir los servicios.|  
|esquema XML|[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) y [esquema XML parte 1: estructuras, segunda edición](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF utiliza el esquema XML para describir tipos de datos usados en los mensajes.|  
|Directiva WS|[Directiva de servicios Web 1.2 - Framework (WS-Policy)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Directiva de servicios Web 1.5 - Framework](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF usa la especificación del WS-Policy 1.2 ó 1.5 con las aserciones específicas del dominio para describir funciones y requisitos de servicio.|  
|Datos adjuntos de directivas WS|[Directiva de servicios Web 1.2: datos adjuntos (WS-PolicyAttachment)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF implementa datos adjuntos de WS-Policy para adjuntar expresiones de directivas en varios ámbitos de WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de servicios Web (WS-MetadataExchange) versión 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0 - enlace WSDL](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF implementa WS-Addressing Binding para que WSDL Adjunte información del direccionamiento en WSDL.|  
  
## <a name="see-also"></a>Vea también  
 [Protocolos de servicios web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [WSDL y directivas](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
