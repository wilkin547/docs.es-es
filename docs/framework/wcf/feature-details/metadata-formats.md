---
title: Formatos de metadatos
ms.date: 03/30/2017
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
ms.openlocfilehash: 55f68f4b56e50b19da19ecc941e9ec537b846006
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62038576"
---
# <a name="metadata-formats"></a>Formatos de metadatos
Windows Communication Foundation (WCF) admite los formatos de metadatos en la tabla siguiente.  
  
## <a name="metadata-specifications-and-usage"></a>Uso y especificaciones de los metadatos  
  
|Protocolo|Especificación y uso|  
|--------------|-----------------------------|  
|WSDL 1.1|[Lenguaje de descripción de servicios Web (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF usa el lenguaje de descripción de servicios Web (WSDL) para describir los servicios.|  
|esquema XML|[Esquema XML parte 2: Los tipos de datos segunda edición](https://go.microsoft.com/fwlink/?LinkId=94861) y [esquema XML parte 1: Segunda edición de estructuras](https://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> WCF usa el esquema XML para describir los tipos de datos usados en los mensajes.|  
|Directiva WS|[Directiva de servicios Web 1.2 – marco de trabajo (WS-Policy)](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Directiva de servicios Web 1.5 - Framework](https://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> WCF usa el WS-Policy 1.2 ó 1.5 con las aserciones específicas del dominio para describir las capacidades y requisitos de servicio.|  
|Datos adjuntos de directivas WS|[Directiva de servicios Web 1.2 – datos adjuntos (WS-PolicyAttachment)](https://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> WCF implementa datos adjuntos de WS-Policy para adjuntar expresiones de directiva en diversos ámbitos de WSDL.|  
|Intercambio de metadatos WS|[Intercambio de metadatos de servicios Web (WS-MetadataExchange) versión 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF implementa WS-MetadataExchange para recuperar el esquema XML, WSDL y WS-Policy.|  
|Enlace de direccionamiento de WS para WSDL|[Web Services Addressing 1.0 – enlace WSDL](https://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> WCF implementa WS-Addressing Binding para que WSDL Adjunte información del direccionamiento en WSDL.|  
  
## <a name="see-also"></a>Vea también

- [Protocolos de servicios web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [WSDL y directivas](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
