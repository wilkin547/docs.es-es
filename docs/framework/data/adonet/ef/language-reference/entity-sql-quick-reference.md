---
title: "Referencia r&#225;pida de Entity SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Referencia r&#225;pida de Entity SQL
Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  Las consultas de este tema se basan en el modelo AdventureWorks Sales.  
  
## Literales  
  
### String  
 Hay literales de cadenas de caracteres Unicode y no Unicode.  Las cadenas Unicode van precedidas de una N.  Por ejemplo: `N'hello'`.  
  
 A continuación se incluye un ejemplo de un literal de cadena no Unicode:  
  
```  
'hello'  
--same as  
"hello"  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|hello|  
  
### DateTime  
 En los literales DateTime, las partes de fecha y hora son obligatorias.  No hay valores predeterminados.  
  
 Ejemplo:  
  
```  
DATETIME '2006-12-25 01:01:00.000'   
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|25.12.06 01:01:00|  
  
### Integer  
 Los literales enteros pueden ser de tipo Int32 \(123\), UInt32 \(123U\), Int64 \(123L\) y UInt64 \(123UL\).  
  
 Ejemplo:  
  
```  
--a collection of integers  
{1, 2, 3}  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|1|  
|2|  
|3|  
  
### Otros  
 Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float\/Double, Decimal y `null`.  Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.  
  
## Constructores de tipos  
  
### ROW  
 [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) crea un valor \(registro\) anónimo escrito estructuralmente como en: `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Ejemplo:  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 Resultado:  
  
|ProductID|Name|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All\-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### MULTISET  
 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) crea colecciones, como:  
  
 `MULTISET(1,2,2,3)` `--same as`\-`{1,2,2,3}.`  
  
 Ejemplo:  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Resultado:  
  
|ProductID|Name|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring\-Panniers, Large|PA\-T100|…|  
  
### Objeto  
 [Constructor de tipos con nombre](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) crea objetos definidos por el usuario \(con nombre\), como `person("abc", 12)`.  
  
 Ejemplo:  
  
```  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,   
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,   
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail   
AS o  
```  
  
 Resultado:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911\-403C\-98|1|776|...|  
|2|4911\-403C\-98|3|777|...|  
|...|...|...|...|...|  
  
## Referencias  
  
### REF  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea una referencia a una instancia de un tipo de entidad.  Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:  
  
```  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 En el ejemplo siguiente se usa el operador de extracción de propiedades \(.\) para tener acceso a una propiedad de una entidad.  Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.  
  
 Ejemplo:  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### DEREF  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) elimina la referencia de un valor de referencia y genera el resultado de dicha eliminación.  Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Ejemplo:  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### CREATEREF y KEY  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea una referencia que pasa una clave.  [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrae la parte de clave de una expresión con referencia de tipos.  
  
 Ejemplo:  
  
```  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))   
    FROM AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## Funciones  
  
### Canónicas  
 El espacio de nombres para las [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) es Edm, como en `Edm.Length("string")`.  No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica.  Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.  
  
 Ejemplo:  
  
```  
SELECT Length(c. FirstName) As NameLen FROM   
    AdventureWorksEntities.Contact AS c   
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 Resultado:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### Específicas de proveedores de Microsoft  
 Las [funciones específicas de proveedores de Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) están en el espacio de nombres `SqlServer`.  
  
 Ejemplo:  
  
```  
SELECT SqlServer.LEN(c.EmailAddress) As EmailLen FROM   
    AdventureWorksEntities.Contact AS c WHERE   
    c.ContactID BETWEEN 10 AND 12  
```  
  
 Resultado:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## Espacios de nombres  
 [USING](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) especifica los espacios de nombres que se usan en una expresión de consulta.  
  
 Ejemplo:  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|aa|  
  
## Paginación  
 La paginación se puede expresar declarando las subcláusulas [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) a la cláusula [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
 Ejemplo:  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Resultado:  
  
|Id.|Name|  
|---------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## Agrupar  
 [GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta \([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)\).  
  
 Ejemplo:  
  
```  
SELECT VALUE name FROM AdventureWorksEntities.Product as P   
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Resultado:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## Navegación  
 El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad \(extremo inicial\) a otro \(extremo final\).  [NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) toma el tipo de relación calificado como \<espacio de nombres\>.\<nombre de tipo de relación\>.  Navigate devuelve Ref\<T\> si la cardinalidad del extremo final es 1.  Si la cardinalidad del extremo final es n, se devolverá Collection\<Ref\<T\>\>.  
  
 Ejemplo:  
  
```  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM   
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)   
    FROM AdventureWorksEntities.Address AS a  
```  
  
 Resultado:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## SELECT VALUE y SELECT  
  
### SELECT VALUE  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas.  Solo se puede especificar un elemento en una cláusula SELECT VALUE.  Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a`.  
  
 Ejemplo:  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Name|  
|----------|  
|Adjustable Race|  
|All\-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### SELECT  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también proporciona el constructor de filas para crear filas arbitrarias.  SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.  
  
 Ejemplo:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|Name|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All\-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## EXPRESIÓN CASE  
 La [expresión CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evalúa un conjunto de expresiones booleanas para determinar el resultado.  
  
 Ejemplo:  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|TRUE|  
  
## Vea también  
 [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Información general de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)