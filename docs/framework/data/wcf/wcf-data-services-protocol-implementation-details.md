---
title: Detalles de implementación del protocolo WCF Data Services
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 2302b5577bec3fc4221bc6e5161c87905c38bec3
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900868"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Detalles de implementación del protocolo WCF Data Services
## <a name="odata-protocol-implementation-details"></a>Detalles de implementación del protocolo OData  
El Open Data Protocol (OData) requiere que un servicio de datos que implemente el protocolo proporcione un determinado conjunto mínimo de funcionalidades. Estas funcionalidades se describen en los documentos del protocolo en términos de "debe" y "debe". Otras funciones opcionales se describen en términos de "mayo". En este artículo se describen estas funcionalidades opcionales que no implementa actualmente WCF Data Services.
  
### <a name="support-for-the-format-query-option"></a>Compatibilidad con la opción de consulta $format  
 El protocolo OData es compatible con las fuentes JavaScript Notation (JSON) y Atom, y OData proporciona la opción de consulta del sistema `$format` para permitir que un cliente solicite el formato de la fuente de respuesta. Esta opción de consulta del sistema, si el servicio de datos la admite, debe invalidar el valor del encabezado Accept de la solicitud. WCF Data Services admite la devolución de fuentes JSON y Atom. Sin embargo, la implementación predeterminada no admite la opción de consulta `$format` y usa solo el valor del encabezado Accept para determinar el formato de la respuesta. Hay casos en los que el servicio de datos quizás necesite admitir la opción de consulta `$format`, como cuando los clientes no pueden establecer el encabezado Accept. Para admitir estos escenarios, debe extender su servicio de datos para administrar esta opción en el URI. Puede Agregar esta funcionalidad al servicio de datos descargando el [JSONP y la compatibilidad con el formato controlado por la dirección URL de ADO.NET Data Services](https://go.microsoft.com/fwlink/?LinkId=208228) proyecto de ejemplo en el sitio web de la galería de código de MSDN y agregándolo a su proyecto de servicio de datos. Este ejemplo quita la opción de consulta `$format` y cambia el encabezado Accept a `application/json`. Al incluir el proyecto de ejemplo y agregar `JSONPSupportBehaviorAttribute` a la clase del servicio de datos permite al servicio administrar la opción de consulta `$format``$format=json`. Se requiere mayor personalización de este proyecto de ejemplo para administrar también `$format=atom` u otros formatos personalizados.  
  
## <a name="wcf-data-services-behaviors"></a>Comportamientos de WCF Data Services  
 Los siguientes comportamientos de WCF Data Services no están definidos explícitamente por el protocolo OData:  
  
### <a name="default-sorting-behavior"></a>Comportamiento de ordenación predeterminado  
 Cuando una solicitud de consulta que se envía al servicio de datos incluye una opción de consulta del sistema `$top` o `$skip` y no incluye la opción de consulta del sistema `$orderby`, las propiedades clave ordenan la fuente devuelta en sentido ascendente. Esto es porque se necesita la ordenación para asegurar la correcta paginación de los resultados. Para ello, el servicio de datos agrega una expresión de ordenación a la consulta. Este comportamiento también se produce cuando la paginación controlada por servidor está habilitada en el servicio de datos. Para obtener más información, vea [configurar el servicio de datos](configuring-the-data-service-wcf-data-services.md). Para controlar el orden de la fuente devuelta, debe incluir `$orderby` en el URI de la consulta.  
  
## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)
