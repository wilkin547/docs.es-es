---
title: Detalles de implementación del protocolo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: a9b996671f2d8b57593f80fb13e966c5f03a2801
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190395"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Detalles de implementación del protocolo WCF Data Services

## <a name="odata-protocol-implementation-details"></a>Detalles de implementación del protocolo OData  

El Open Data Protocol (OData) requiere que un servicio de datos que implemente el protocolo proporcione un determinado conjunto mínimo de funcionalidades. Estas funcionalidades se describen en los documentos del protocolo en términos de "debe" y "debe". Otras funciones opcionales se describen en términos de "mayo". En este artículo se describen estas funcionalidades opcionales que no implementa actualmente WCF Data Services.
  
### <a name="support-for-the-format-query-option"></a>Compatibilidad con la opción de consulta $format  

 El protocolo OData es compatible con las fuentes JavaScript Notation (JSON) y Atom, y OData proporciona la `$format` opción de consulta del sistema para permitir a un cliente solicitar el formato de la fuente de respuesta. Esta opción de consulta del sistema, si el servicio de datos la admite, debe invalidar el valor del encabezado Accept de la solicitud. WCF Data Services admite la devolución de fuentes JSON y Atom. Sin embargo, la implementación predeterminada no admite la opción de consulta `$format` y usa solo el valor del encabezado Accept para determinar el formato de la respuesta. Hay casos en los que el servicio de datos quizás necesite admitir la opción de consulta `$format`, como cuando los clientes no pueden establecer el encabezado Accept. Para admitir estos escenarios, debe extender su servicio de datos para administrar esta opción en el URI.
  
## <a name="wcf-data-services-behaviors"></a>Comportamientos de WCF Data Services  

 Los siguientes comportamientos de WCF Data Services no están definidos explícitamente por el protocolo OData:  
  
### <a name="default-sorting-behavior"></a>Comportamiento de ordenación predeterminado  

 Cuando una solicitud de consulta que se envía al servicio de datos incluye una opción de consulta del sistema `$top` o `$skip` y no incluye la opción de consulta del sistema `$orderby`, las propiedades clave ordenan la fuente devuelta en sentido ascendente. Esto es porque se necesita la ordenación para asegurar la correcta paginación de los resultados. Para ello, el servicio de datos agrega una expresión de ordenación a la consulta. Este comportamiento también se produce cuando la paginación controlada por servidor está habilitada en el servicio de datos. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md). Para controlar el orden de la fuente devuelta, debe incluir `$orderby` en el URI de la consulta.  
  
## <a name="see-also"></a>Consulta también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
