---
title: Control de versiones del servicio de datos (Data Services de Microsoft WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: f82ab4c98e724bbed658a6c77de9c5a5d5c3390f
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121538"
---
# <a name="data-service-versioning-wcf-data-services"></a>Control de versiones del servicio de datos (Data Services de Microsoft WCF)
El protocolo de datos abiertos (OData) le permite crear servicios de datos para que los clientes puedan tener acceso a los datos como recursos mediante URI basados en un modelo de datos. OData también admite la definición de operaciones de servicio. Después de la implementación inicial y de haber transcurrido potencialmente varias horas durante su duración, estos servicios de datos pueden necesitar ser cambiados debido a diversas razones, como cambios en las necesidades comerciales, requisitos de tecnología de la información o para resolver otros problemas. Al realizar cambios en un servicio de datos existente, debe considerar si va a definir una nueva versión de su servicio de datos y cómo minimizar mejor el impacto en las aplicaciones cliente existentes. En este tema se proporciona orientación sobre cuándo y cómo crear una nueva versión de un servicio de datos. También describe cómo SERVICIOS de datos de WCFWCF Data Services controla un intercambio entre clientes y servicios de datos que admiten diferentes versiones del protocolo OData.

## <a name="versioning-a-wcf-data-service"></a>Control de versiones de WCF Data Services
 Una vez implementado un servicio de datos y usados los datos, los cambios realizados al servicio de datos tienen el potencial para producir problemas de compatibilidad con las aplicaciones cliente existentes. Sin embargo, como las necesidades del negocio totales del servicio requieren a menudo cambios, debe considerar cuándo y cómo crear una nueva versión de su servicio de datos con el menor impacto para las aplicaciones cliente.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Cambios del modelo de datos que recomiendan una nueva versión del servicio de datos
 Al considerar si se va a publicar una nueva versión de un servicio de datos, es importante entender cómo los diferentes tipos de cambios pueden afectar a las aplicaciones cliente. Los cambios de un servicio de datos que podrían requerir crear una nueva versión de un servicio de datos se pueden dividir en las siguientes dos categorías:

- Los cambios del contrato de servicio —que incluyen actualizaciones de las operaciones de servicio, cambios de la accesibilidad de conjuntos de entidades (fuentes), cambios de versiones y otros cambios de los comportamientos del servicio.

- Los cambios del contrato de datos —que incluyen cambios del modelo de datos, formatos de fuente o personalización de la fuente.

 La tabla siguiente detalla para qué clases de cambios debe considerar la posibilidad de publicar una nueva versión del servicio de datos:

|Tipo de cambio|Requiere una nueva versión|No se necesita una nueva versión|
|--------------------|----------------------------|----------------------------|
|Operaciones de servicio|- Añadir nuevo parámetro<br />- Cambiar el tipo de devolución<br />- Eliminar la operación de servicio|- Eliminar parámetro existente<br />- Añadir nueva operación de servicio|
|Comportamientos de servicio|- Deshabilitar las solicitudes de recuento<br />- Deshabilitar el soporte de proyección<br />- Aumentar la versión de servicio de datos requerida|- Habilitar solicitudes de recuento<br />- Activar soporte de proyección<br />- Disminuir la versión de servicio de datos requerida|
|Permisos del conjunto de entidades|- Restringir los permisos de conjunto de entidades<br />- Cambiar el código de respuesta (nuevo valor de primer dígito) <sup>1</sup>|- Permisos de conjunto de entidades de relajación<br />- Cambiar el código de respuesta (mismo valor de primer dígito)|
|Propiedades de entidad|- Eliminar la propiedad o relación existente<br />- Añadir propiedad que no acepta valores NULL<br />- Cambiar la propiedad existente|- Añadir propiedad que acepta valores NULL<sup>2</sup>|
|Conjuntos de entidades|- Eliminar conjunto de entidades|- Añadir tipo derivado<br />- Cambiar el tipo de base<br />- Añadir conjunto de entidades|
|Personalización de fuentes|- Cambiar el mapeo entidad-propiedad||

 <sup>1</sup> Esto puede depender de la estrictamente una aplicación cliente se basa en la recepción de un código de error específico.

 <sup>2</sup> Puede establecer <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> la `true` propiedad para que el cliente ignore las nuevas propiedades enviadas por el servicio de datos que no están definidas en el cliente. Sin embargo, cuando se realizan inserciones, las propiedades no incluidas por el cliente en la solicitud POST se establecen en sus valores predeterminados. Para las actualizaciones, cualquier dato existente en una propiedad desconocida para el cliente podría sobrescribirse con los valores predeterminados. En este caso, debería enviar la actualización como una solicitud MERGE, que es el valor predeterminado. Para obtener más información, consulte [Administración del contexto del servicio](managing-the-data-service-context-wcf-data-services.md)de datos .

### <a name="how-to-version-a-data-service"></a>Cómo controlar las versiones de un servicio de datos
 Cuando se requiere, una nueva versión del servicio de datos se define creando una nueva instancia del servicio con un contrato de servicio o un modelo de datos actualizado. A continuación, este nuevo servicio se expone usando un nuevo punto de conexión de URI, que lo diferencia de la versión anterior. Por ejemplo:

- La versión anterior: `http://services.odata.org/Northwind/v1/Northwind.svc/`

- Nueva versión: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Al actualizar un servicio de datos, los clientes necesitarán también estar actualizados según los nuevos metadatos del servicio de datos y usar el nuevo URI raíz. Cuando sea posible, debe mantener la versión anterior del servicio de datos para admitir clientes que todavía no se hayan actualizado para usar la nueva versión. Se pueden quitar las versiones anteriores de un servicio de datos cuando ya no se necesitan. Debe considerar la posibilidad de mantener el URI del punto de conexión del servicio de datos en un archivo de configuración externo.

## <a name="odata-protocol-versions"></a>Versiones del protocolo OData
 A medida que se publican nuevas versiones de OData, es posible que las aplicaciones cliente no usen la misma versión del protocolo OData compatible con el servicio de datos. Una aplicación cliente anterior puede tener acceso a un servicio de datos que admite una versión más reciente de OData. Una aplicación cliente también puede usar una versión más reciente de la biblioteca de cliente de Servicios de datos de WCFWCF Data Services, que admite una versión más reciente de OData que el servicio de datos al que se tiene acceso.

 Servicios de datos de WCFWCF Data Services aprovecha la compatibilidad proporcionada por OData para controlar estos escenarios de control de versiones. También hay compatibilidad para generar y usar metadatos del modelo de datos para crear clases de servicio de datos de cliente cuando el cliente usa una versión diferente de OData que el servicio de datos usa. Para obtener más información, consulte la sección Control de versiones de protocolo en el artículo [OData: Información general.](https://www.odata.org/documentation/odata-version-2-0/overview/)

### <a name="version-negotiation"></a>Negociación de las versiones
 El servicio de datos se puede configurar para definir la versión más alta del protocolo OData que usará el servicio, independientemente de la versión solicitada por el cliente. Puede hacerlo especificando un <xref:System.Data.Services.Common.DataServiceProtocolVersion> valor <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> para la <xref:System.Data.Services.DataServiceBehavior> propiedad de la utilizada por el servicio de datos. Para obtener más información, consulte [Configuración del servicio](configuring-the-data-service-wcf-data-services.md)de datos .

 Cuando una aplicación usa las bibliotecas de cliente de Servicios de datos de WCFWCF Data Services para tener acceso a un servicio de datos, las bibliotecas establecen automáticamente estos encabezados en los valores correctos, dependiendo de la versión de OData y las características que se usan en la aplicación. De forma predeterminada, Servicios de datos de WCFWCF Data Services usa la versión de protocolo más baja que admite la operación solicitada.

 En la tabla siguiente se detallan las versiones de .NET Framework y Silverlight que incluyen compatibilidad con Servicios de datos de WCFWCF Data Services para versiones específicas del protocolo OData.

|Versión del protocolo OData|Compatibilidad introducida en…|
|-----------------------------------------------------------------------------------|----------------------------|
|versión 1|- .NET Framework 3.5 Service Pack 1 (SP1)<br />- Silverlight versión 3|
|versión 2|- .NET Framework 4<br />- Silverlight versión 4|

### <a name="metadata-versions"></a>Versiones de metadatos
 De forma predeterminada, Servicios de datos de WCFWCF Data Services usa la versión 1.1 de CSDL para representar un modelo de datos. Este siempre es el caso para los modelos de datos basados en un proveedor de reflexión o en un proveedor del servicio de datos personalizados. No obstante, cuando se define un modelo de datos mediante Entity Framework, la versión devuelta de CSDL es la misma que la que usa Entity Framework. La versión del CSDL viene determinada por el espacio de nombres del [elemento Schema (CSDL).](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#schema-element-csdl)

 El elemento `DataServices` de los metadatos devueltos también contiene un atributo `DataServiceVersion`, que tiene el mismo valor que el encabezado `DataServiceVersion` del mensaje de respuesta. Las aplicaciones cliente, como el **agregar referencia** de servicio cuadro de diálogo en Visual Studio, usan esta información para generar clases de servicio de datos de cliente que funcionan correctamente con la versión de WCF Data Services que hospedan el servicio de datos. Para obtener más información, consulte la sección Control de versiones de protocolo en el artículo [OData: Información general.](https://www.odata.org/documentation/odata-version-2-0/overview/)

## <a name="see-also"></a>Vea también

- [Proveedores de Data Services](data-services-providers-wcf-data-services.md)
- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
