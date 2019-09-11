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
ms.openlocfilehash: 048cbb8708aa705fe6b03491ddfa9c107a21cda1
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894351"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Acceder a recursos de servicios de datos (Servicios de datos de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)][!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] admite para exponer los datos como una fuente con recursos direccionables mediante URI. Estos recursos se representan según las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md). En este modelo, las entidades representan unidades operacionales de datos que son tipos de datos en un dominio de aplicación, como clientes, pedidos, elementos y productos. El acceso a los datos de entidad y la modificación de los mismos se realiza usando la semántica de Representational State Transfer (REST), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE.  
  
## <a name="addressing-resources"></a>Direccionar recursos  
 En [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], podrá direccionar los datos expuestos por el modelo de datos utilizando un URI. Por ejemplo, el siguiente URI devuelve una fuente que es el conjunto de entidades customers, que contiene entradas para todas las instancias del tipo de entidad Customer:  
  
```http
https://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Las entidades tienen propiedades especiales denominadas claves de entidad. Una clave de entidad se usa para identificar una entidad única de manera unívoca en un conjunto de entidades. Esto le permite direccionar una instancia concreta de un tipo de entidad en el conjunto de entidades. Por ejemplo, el siguiente URI devuelve la entrada de una instancia concreta del tipo de entidad Customer que tiene el valor de clave `ALFKI`:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 También se pueden direccionar individualmente las propiedades primitivas y complejas de una instancia de entidad. Por ejemplo, el siguiente URI devuelve un elemento XML que contiene el valor de propiedad `ContactName` para una entidad Customer concreta:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 Al incluir el punto de conexión `$value` en el URI anterior, en el mensaje de respuesta solamente se devuelve el valor de propiedad primitiva. En el siguiente ejemplo solo se devuelve la cadena "Maria Anders" sin el elemento XML:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Las relaciones entre entidades se definen en el modelo de datos mediante asociaciones. Estas asociaciones le permiten direccionar entidades relacionadas mediante propiedades de navegación de una instancia de entidad. Una propiedad de navegación puede devolver una única entidad relacionada, en el caso de una relación de varios a uno, o un conjunto de entidades relacionadas, en el caso de una relación de uno a varios. Por ejemplo, el siguiente URI devuelve una fuente que representa el conjunto de todas las entidades Orders relacionadas con una entidad Customer concreta:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Las relaciones, que son con frecuencia bidireccionales, están representadas por un par de propiedades de navegación. Al contrario de la relación mostrada en el ejemplo anterior, el siguiente URI devuelve una referencia a la entidad Customer a la que pertenece una entidad Order concreta:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]también permite direccionar recursos basándose en los resultados de las expresiones de consulta. Esto permite filtrar conjuntos de recursos en función de una expresión evaluada. Por ejemplo, el siguiente URI filtra los recursos para devolver al Customer especificado solo los Orders (pedidos) que se han distribuido desde el 22 de septiembre de 1997:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Para obtener más información, [consulte OData: Convenciones](https://go.microsoft.com/fwlink/?LinkId=185564)de URI.  
  
## <a name="system-query-options"></a>Opciones de consulta del sistema  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]define un conjunto de opciones de consulta del sistema que puede utilizar para realizar operaciones de consulta tradicionales en los recursos, como filtrado, ordenación y paginación. Por ejemplo, el siguiente URI devuelve el conjunto de todas las `Order` entidades, junto con las `Order_Detail` entidades relacionadas, cuyos códigos postales no terminan en `100`:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Las entradas de la fuente devuelta se ordenan también en función del valor de propiedad ShipCity de los pedidos.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]admite las siguientes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] opciones de consulta del sistema:  
  
|Opción de consulta|DESCRIPCIÓN|  
|------------------|-----------------|  
|`$orderby`|Define un criterio de ordenación predeterminado para las entidades de la fuente devuelta. La siguiente consulta ordena la fuente de los clientes devuelta por provincia y ciudad:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Para obtener más información, [consulte OData: Opción de consulta del sistema OrderBy (](https://go.microsoft.com/fwlink/?LinkId=186968)$OrderBy).|  
|`$top`|Especifica el número de entidades que se incluirán en la fuente devuelta. En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Para obtener más información, [consulte OData: Opción de consulta de sistema superior (](https://go.microsoft.com/fwlink/?LinkId=186969)$Top).|  
|`$skip`|Especifica el número de entidades que se omitirán antes de empezar a devolver las entidades en la fuente. En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Para obtener más información, [consulte OData: Opción omitir consulta del sistema (](https://go.microsoft.com/fwlink/?LinkId=186971)$SKIP).|  
|`$filter`|Define una expresión que filtra las entidades devueltas en la fuente en función de criterios concretos. Esta opción de consulta admite un conjunto de operadores de comparación lógicos, operadores aritméticos y funciones de consulta predefinidas que se utilizan para evaluar la expresión de filtro. En el siguiente ejemplo se devuelven todos los pedidos cuyo código postal no termina en 100:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Para obtener más información, [consulte OData: Opción de consulta del sistema Filter (](https://go.microsoft.com/fwlink/?LinkId=186972)$Filter).|  
|`$expand`|Especifica qué entidades relacionadas devuelve la consulta. Las entidades relacionadas se incluyen como una fuente o una entrada alineada con la entidad devuelta por la consulta. En el siguiente ejemplo se devuelve el pedido del cliente 'ALFKI' junto con los detalles de artículos de cada pedido:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Para obtener más información, [consulte OData: Expanda opción de consulta del sistema](https://go.microsoft.com/fwlink/?LinkId=186973)($Expand).|  
|`$select`|Especifica una proyección que define las propiedades de la entidad devueltas en la proyección. De forma predeterminada, todas las propiedades de una entidad se devuelven en una fuente. La siguiente consulta devuelve solo tres propiedades de la entidad `Customer`:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Para obtener más información, [consulte OData: Seleccione la opción de consulta del sistema](https://go.microsoft.com/fwlink/?LinkID=186076)($Select).|  
|`$inlinecount`|Solicita que se incluya con la fuente un recuento del número de entidades devuelto en la fuente. Para obtener más información, [consulte OData: Opción de consulta del sistema Inlinecount (](https://go.microsoft.com/fwlink/?LinkId=186975)$inlinecount).|  
  
## <a name="addressing-relationships"></a>Direccionar relaciones  
 Además de direccionar conjuntos de entidades e instancias de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] entidad, también permite direccionar las asociaciones que representan las relaciones entre las entidades. Esta funcionalidad es necesaria para crear o cambiar una relación entre dos instancias de entidades, como el expedidor relacionado con un pedido determinado de la base de datos de ejemplo Northwind. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]admite un `$link` operador para direccionar específicamente las asociaciones entre las entidades. Por ejemplo, el URI siguiente se especifica en un mensaje de solicitud PUT de HTTP para que se use otro expedidor para el pedido especificado  
  
```http 
https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Para obtener más información, [consulte OData: Direccionar vínculos entre](https://go.microsoft.com/fwlink/?LinkId=187351)entradas.  
  
## <a name="consuming-the-returned-feed"></a>Utilizar la fuente devuelta  
 El URI de un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] recurso permite direccionar los datos de la entidad expuestos por el servicio. Cuando se escribe un URI en el campo de dirección de un explorador Web, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] se devuelve una representación de la fuente del recurso solicitado. Para obtener más información, consulte la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md). Aunque un explorador Web puede ser útil para probar que un recurso del servicio de datos devuelve los datos esperados, los servicios de datos de producción que también pueden crear, actualizar y eliminar datos suelen tener acceso mediante código de aplicación o lenguajes de scripting en una página web. Para obtener más información, consulte [uso de un servicio de datos en una aplicación cliente](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Vea también

- [Sitio web de Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=182204)
