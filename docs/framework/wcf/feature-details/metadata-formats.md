---
title: Formatos de metadatos
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 01f0d7a2212b2af7e2d3a959ed91624edec46ce8
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720470"
---
# <a name="metadata-formats"></a>Formatos de metadatos

Windows Communication Foundation (WCF) es compatible con los formatos de metadatos de la tabla siguiente.  
  
## <a name="metadata-specifications-and-usage"></a>Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web (WSDL) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF usa el lenguaje de descripción de servicios web (WSDL) para describir los servicios.|  
|esquema XML|[Esquema XML parte 2: tipos](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) de archivo de segunda edición y [esquema XML parte 1: segunda edición de estructuras](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF usa el esquema XML para describir los tipos de datos que se usan en los mensajes.|  
|Directiva WS|[Directiva de servicios web 1.2 – Marco de trabajo (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Directiva de servicios web 1.5 – Marco de trabajo](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF usa las especificaciones de WS-Policy 1,2 o 1,5 con las aserciones específicas del dominio para describir los requisitos de servicio y las capacidades.|  
|Datos adjuntos de directivas WS|[Directiva de servicios web 1.2 – Datos adjuntos (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF implementa datos adjuntos de WS-Policy para adjuntar expresiones de directiva en varios ámbitos en WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de servicios web  (WS-MetadataExchange) versión 1.1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0 – Enlace WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF implementa el enlace WS-Addressing para que WSDL adjunte información de direccionamiento en WSDL.|  
  
## <a name="see-also"></a>Vea también

- [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL y directivas](wsdl-and-policy.md)
