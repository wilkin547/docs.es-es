---
title: Acceder a recursos de servicios de datos (Servicios de datos de WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
ms.openlocfilehash: 6a44d61f29fad7fa7d5304deb8b1e329478bc5b4
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202019"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Acceder a recursos de servicios de datos (Servicios de datos de WCF)
WCF Data Services admite el Open Data Protocol (OData) para exponer los datos como una fuente con recursos direccionables mediante URI. Estos recursos se representan según las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md). En este modelo, las entidades representan unidades operacionales de datos que son tipos de datos en un dominio de aplicación, como clientes, pedidos, elementos y productos. El acceso a los datos de entidad y la modificación de los mismos se realiza usando la semántica de Representational State Transfer (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE.  
  
## <a name="addressing-resources"></a>Direccionar recursos  
 En OData, se abordan los datos expuestos por el modelo de datos mediante un URI. Por ejemplo, el siguiente URI devuelve una fuente que representa el conjunto de entidades Customers, que contiene las entradas de todas las instancias del tipo de entidad Customer:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers>
  
 Las entidades tienen propiedades especiales denominadas claves de entidad. Una clave de entidad se usa para identificar una entidad única de manera unívoca en un conjunto de entidades. Esto le permite direccionar una instancia concreta de un tipo de entidad en el conjunto de entidades. Por ejemplo, el siguiente URI devuelve la entrada de una instancia concreta del tipo de entidad Customer que tiene el valor de clave `ALFKI`:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')>
  
 También se pueden direccionar individualmente las propiedades primitivas y complejas de una instancia de entidad. Por ejemplo, el siguiente URI devuelve un elemento XML que contiene el valor de propiedad `ContactName` para una entidad Customer concreta:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName>
  
 Al incluir el punto de conexión `$value` en el URI anterior, en el mensaje de respuesta solamente se devuelve el valor de propiedad primitiva. En el siguiente ejemplo solo se devuelve la cadena "Maria Anders" sin el elemento XML:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value>
  
 Las relaciones entre entidades se definen en el modelo de datos mediante asociaciones. Estas asociaciones le permiten direccionar entidades relacionadas mediante propiedades de navegación de una instancia de entidad. Una propiedad de navegación puede devolver una única entidad relacionada, en el caso de una relación de varios a uno, o un conjunto de entidades relacionadas, en el caso de una relación de uno a varios. Por ejemplo, el siguiente URI devuelve una fuente que representa el conjunto de todas las entidades Orders relacionadas con una entidad Customer concreta:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders>
  
 Las relaciones, que son con frecuencia bidireccionales, están representadas por un par de propiedades de navegación. Al contrario de la relación mostrada en el ejemplo anterior, el siguiente URI devuelve una referencia a la entidad Customer a la que pertenece una entidad Order concreta:  
  
<https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer>
  
 OData también permite direccionar recursos basándose en los resultados de las expresiones de consulta. Esto permite filtrar conjuntos de recursos en función de una expresión evaluada. Por ejemplo, el siguiente URI filtra los recursos para devolver al Customer especificado solo los Orders (pedidos) que se han distribuido desde el 22 de septiembre de 1997:  
  
`https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'`
  
 Para obtener más información, vea [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="system-query-options"></a>Opciones de consulta del sistema  
 OData define un conjunto de opciones de consulta del sistema que puede usar para realizar operaciones de consulta tradicionales en recursos, como filtrado, ordenación y paginación. Por ejemplo, el siguiente URI devuelve el conjunto de todas las `Order` entidades, junto con `Order_Detail` las entidades relacionadas, cuyos códigos postales no terminan en `100` :  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity`
  
 Las entradas de la fuente devuelta se ordenan también en función del valor de propiedad ShipCity de los pedidos.  
  
 WCF Data Services admite las siguientes opciones de consulta del sistema OData:  
  
|Opción de consulta|Descripción|  
|------------------|-----------------|  
|`$orderby`|Define un criterio de ordenación predeterminado para las entidades de la fuente devuelta. La siguiente consulta ordena la fuente de los clientes devuelta por provincia y ciudad:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City>`|  
|`$top`|Especifica el número de entidades que se incluirán en la fuente devuelta. En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$skip`|Especifica el número de entidades que se omitirán antes de empezar a devolver las entidades en la fuente. En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$filter`|Define una expresión que filtra las entidades devueltas en la fuente en función de criterios concretos. Esta opción de consulta admite un conjunto de operadores de comparación lógicos, operadores aritméticos y funciones de consulta predefinidas que se utilizan para evaluar la expresión de filtro. En el siguiente ejemplo se devuelven todos los pedidos cuyo código postal no termina en 100:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`|  
|`$expand`|Especifica qué entidades relacionadas devuelve la consulta. Las entidades relacionadas se incluyen como una fuente o una entrada alineada con la entidad devuelta por la consulta. En el siguiente ejemplo se devuelve el pedido del cliente 'ALFKI' junto con los detalles de artículos de cada pedido:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`|  
|`$select`|Especifica una proyección que define las propiedades de la entidad devueltas en la proyección. De forma predeterminada, todas las propiedades de una entidad se devuelven en una fuente. La siguiente consulta devuelve solo tres propiedades de la entidad `Customer`:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`|  
|`$inlinecount`|Solicita que se incluya con la fuente un recuento del número de entidades devuelto en la fuente.|  
  
## <a name="addressing-relationships"></a>Direccionar relaciones  
 Además de direccionar conjuntos de entidades e instancias de entidad, OData también permite direccionar las asociaciones que representan las relaciones entre las entidades. Esta funcionalidad es necesaria para crear o cambiar una relación entre dos instancias de entidades, como el expedidor relacionado con un pedido determinado de la base de datos de ejemplo Northwind. OData admite un `$link` operador para direccionar específicamente las asociaciones entre las entidades. Por ejemplo, el URI siguiente se especifica en un mensaje de solicitud PUT de HTTP para que se use otro expedidor para el pedido especificado  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper`
  
 Para obtener más información, vea la sección `3.2. Addressing Links between Entries` en [OData: convenciones de URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="consuming-the-returned-feed"></a>Utilizar la fuente devuelta  
 El URI de un recurso de OData permite direccionar los datos de la entidad expuestos por el servicio. Cuando se escribe un URI en el campo de dirección de un explorador Web, se devuelve una representación de la fuente de OData del recurso solicitado. Para obtener más información, consulte la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md). Aunque un explorador web puede ser útil para probar que un recurso del servicio de datos devuelve los datos esperados, normalmente el acceso a los servicios de datos de producción -que también pueden crear, actualizar y eliminar datos- se realiza mediante código de aplicación o lenguajes de scripting en una página web. Para obtener más información, consulte [uso de un servicio de datos en una aplicación cliente](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Consulta también

- [Sitio web de Open Data Protocol](https://www.odata.org/)
