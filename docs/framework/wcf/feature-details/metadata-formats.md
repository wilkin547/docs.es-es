---
description: 'Más información sobre: formatos de metadatos'
title: Formatos de metadatos
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: f8c5d6dd5c75f38d4114f6232e9d1d6048a8343e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733923"
---
# <a name="metadata-formats"></a>Formatos de metadatos

Windows Communication Foundation (WCF) es compatible con los formatos de metadatos de la tabla siguiente.  
  
## <a name="metadata-specifications-and-usage"></a>Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web (WSDL) 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF usa el lenguaje de descripción de servicios web (WSDL) para describir los servicios.|  
|esquema XML|[Esquema XML parte 2: tipos](https://www.w3.org/TR/2004/REC-xmlschema-2-20041028/) de archivo de segunda edición y [esquema XML parte 1: segunda edición de estructuras](https://www.w3.org/TR/2004/REC-xmlschema-1-20041028/)<br /><br /> WCF usa el esquema XML para describir los tipos de datos que se usan en los mensajes.|  
|Directiva WS|[Directiva de servicios web 1.2 – Marco de trabajo (WS-Policy)](https://www.w3.org/Submission/WS-Policy/)<br /><br /> [Directiva de servicios web 1.5 – Marco de trabajo](https://www.w3.org/TR/ws-policy/)<br /><br /> WCF usa las especificaciones WS-Policy 1,2 o 1,5 con aserciones específicas del dominio para describir las capacidades y los requisitos del servicio.|  
|Datos adjuntos de directivas WS|[Directiva de servicios web 1.2 – Datos adjuntos (WS-PolicyAttachment)](https://www.w3.org/Submission/WS-PolicyAttachment/)<br /><br /> WCF implementa WS-Policy datos adjuntos para adjuntar expresiones de directiva en varios ámbitos en WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de servicios web  (WS-MetadataExchange) versión 1.1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0 – Enlace WSDL](https://www.w3.org/TR/ws-addr-wsdl/)<br /><br /> WCF implementa WS-Addressing enlace para que WSDL adjunte información de direccionamiento en WSDL.|  
  
## <a name="see-also"></a>Vea también

- [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL y directivas](wsdl-and-policy.md)
