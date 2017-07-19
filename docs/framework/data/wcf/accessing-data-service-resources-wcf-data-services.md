---
title: "Acceso a recursos del servicio de datos (WCF. Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "introducción, Servicios de datos de Microsoft WCF"
  - "consultar el servicio de datos [WCF Data Service]"
  - "WCF Data Services, acceso a datos"
  - "WCF Data Services, introducción"
  - "WCF Data Services, consultar"
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Acceso a recursos del servicio de datos (WCF. Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer los datos como una fuente con recursos direccionables a través de identificadores uniformes de recursos \(URI\).  Estos recursos se representan según las convenciones del modelo entidad\-relación de [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md).  En este modelo, las entidades representan unidades operacionales de datos que son tipos de datos en un dominio de aplicación, como clientes, pedidos, elementos y productos.  El acceso a los datos de entidad y la modificación de los mismos se realiza usando la semántica de Representational State Transfer \(REST\), específicamente los verbos HTTP estándar GET, PUT, POST y DELETE.  
  
## Direccionar recursos  
 En [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], podrá direccionar los datos expuestos por el modelo de datos utilizando un URI.  Por ejemplo, el siguiente URI devuelve una fuente que representa el conjunto de entidades Customers, que contiene las entradas de todas las instancias del tipo de entidad Customer:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Las entidades tienen propiedades especiales denominadas claves de entidad.  Una clave de entidad se usa para identificar una entidad única de manera unívoca en un conjunto de entidades.  Esto le permite direccionar una instancia concreta de un tipo de entidad en el conjunto de entidades.  Por ejemplo, el siguiente URI devuelve la entrada de una instancia concreta del tipo de entidad Customer que tiene el valor de clave `ALFKI`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 También se pueden direccionar individualmente las propiedades primitivas y complejas de una instancia de entidad.  Por ejemplo, el siguiente URI devuelve un elemento XML que contiene el valor de propiedad `ContactName` para una entidad Customer concreta:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 Al incluir el extremo `$value` en el URI anterior, en el mensaje de respuesta solamente se devuelve el valor de propiedad primitiva.  En el siguiente ejemplo solo se devuelve la cadena "Maria Anders" sin el elemento XML:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Las relaciones entre entidades se definen en el modelo de datos mediante asociaciones.  Estas asociaciones le permiten direccionar entidades relacionadas mediante propiedades de navegación de una instancia de entidad.  Una propiedad de navegación puede devolver una única entidad relacionada, en el caso de una relación de varios a uno, o un conjunto de entidades relacionadas, en el caso de una relación de uno a varios.  Por ejemplo, el siguiente URI devuelve una fuente que representa el conjunto de todas las entidades Orders relacionadas con una entidad Customer concreta:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Las relaciones, que son con frecuencia bidireccionales, están representadas por un par de propiedades de navegación.  Al contrario de la relación mostrada en el ejemplo anterior, el siguiente URI devuelve una referencia a la entidad Customer a la que pertenece una entidad Order concreta:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] también le permite direccionar recursos basándose en los resultados de expresiones de consulta.  Esto permite filtrar conjuntos de recursos en función de una expresión evaluada.  Por ejemplo, el siguiente URI filtra los recursos para devolver al Customer especificado solo los Orders \(pedidos\) que se han distribuido desde el 22 de septiembre de 1997:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Para obtener más información, vea el tema sobre [OData: convenciones de URI](http://go.microsoft.com/fwlink/?LinkId=185564).  
  
## Opciones de consulta del sistema  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] define un conjunto de opciones de consulta del sistema que puede utilizar para realizar operaciones de consulta tradicionales en los recursos, como filtrar, ordenar y paginar.  Por ejemplo, el siguiente URI devuelve el conjunto de todas las entidades `Order`, junto con las entidades `Order_Detail` relacionadas, cuyo código postal no termina en `100`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Las entradas de la fuente devuelta se ordenan también en función del valor de propiedad ShipCity de los pedidos.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] admite las siguientes opciones de consulta del sistema de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]:  
  
|Opción de consulta|Descripción|  
|------------------------|-----------------|  
|`$orderby`|Define un criterio de ordenación predeterminado para las entidades de la fuente devuelta.  La siguiente consulta ordena la fuente de los clientes devuelta por provincia y ciudad:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Para obtener más información, vea el tema sobre[OData: opción de consulta del sistema OrderBy \($orderby\)](http://go.microsoft.com/fwlink/?LinkId=186968).|  
|`$top`|Especifica el número de entidades que se incluirán en la fuente devuelta.  En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Top \($top\)](http://go.microsoft.com/fwlink/?LinkId=186969).|  
|`$skip`|Especifica el número de entidades que se omitirán antes de empezar a devolver las entidades en la fuente.  En el siguiente ejemplo se omiten los 10 primeros clientes y, a continuación, se devuelven los 10 siguientes:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Para obtener más información, vea el tema sobre [OData: opción de consulta del Skip \($skip\)](http://go.microsoft.com/fwlink/?LinkId=186971).|  
|`$filter`|Define una expresión que filtra las entidades devueltas en la fuente en función de criterios concretos.  Esta opción de consulta admite un conjunto de operadores de comparación lógicos, operadores aritméticos y funciones de consulta predefinidas que se utilizan para evaluar la expresión de filtro.  En el siguiente ejemplo se devuelven todos los pedidos cuyo código postal no termina en 100:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Filter \($filter\)](http://go.microsoft.com/fwlink/?LinkId=186972).|  
|`$expand`|Especifica qué entidades relacionadas devuelve la consulta.  Las entidades relacionadas se incluyen como una fuente o una entrada alineada con la entidad devuelta por la consulta.  En el siguiente ejemplo se devuelve el pedido del cliente 'ALFKI' junto con los detalles de artículos de cada pedido:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Expand \($expand\)](http://go.microsoft.com/fwlink/?LinkId=186973).|  
|`$select`|Especifica una proyección que define las propiedades de la entidad devueltas en la proyección.  De forma predeterminada, todas las propiedades de una entidad se devuelven en una fuente.  La siguiente consulta devuelve solo tres propiedades de la entidad `Customer`:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Select \($select\)](http://go.microsoft.com/fwlink/?LinkId=186076).|  
|`$inlinecount`|Solicita que se incluya con la fuente un recuento del número de entidades devuelto en la fuente.  Para obtener más información, vea el tema sobre [OData: opción de consulta del sistema Inlinecount \($inlinecount\)](http://go.microsoft.com/fwlink/?LinkId=186975).|  
  
## Direccionar relaciones  
 Además de direccionar conjuntos de entidades e instancias de entidades, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] también permite direccionar las asociaciones que representan las relaciones entre las entidades.  Esta funcionalidad es necesaria para crear o cambiar una relación entre dos instancias de entidades, como el expedidor relacionado con un pedido determinado de la base de datos de ejemplo Northwind.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] admite un operador `$link` para direccionar específicamente las asociaciones entre las entidades.  Por ejemplo, el URI siguiente se especifica en un mensaje de solicitud PUT de HTTP para que se use otro expedidor para el pedido especificado  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Para obtener más información, vea el tema sobre [OData: administrar vínculos entre entradas](http://go.microsoft.com/fwlink/?LinkId=187351).  
  
## Utilizar la fuente devuelta  
 El URI de un recurso de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] permite direccionar datos de entidad expuestos por el servicio.  Al registrar un URI en el campo de dirección de un explorador web, se devuelve una representación de la fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] del recurso solicitado.  Para obtener más información, vea el [Tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Aunque un explorador web puede ser útil para probar que un recurso del servicio de datos devuelve los datos esperados, normalmente el acceso a los servicios de datos de producción \-que también pueden crear, actualizar y eliminar datos\- se realiza mediante código de aplicación o lenguajes de scripting en una página web.  Para obtener más información, consulta [Usar un servicio de datos en una aplicación cliente](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## Vea también  
 [Sitio web de Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=182204)