---
description: 'Más información acerca de: Entity SQL referencia rápida'
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: ddac48bece1f0e9df737db295d4d028529ea290f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724562"
---
# <a name="entity-sql-quick-reference"></a>Referencia rápida de Entity SQL

Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Las consultas de este tema se basan en el modelo AdventureWorks Sales.  
  
## <a name="literals"></a>Literales  
  
### <a name="string"></a>String  

 Hay literales de cadenas de caracteres Unicode y no Unicode. Las cadenas Unicode se anteponen a N. Por ejemplo, `N'hello'` .  
  
 A continuación se incluye un ejemplo de un literal de cadena no Unicode:  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|hello|  
  
### <a name="datetime"></a>DateTime  

 En los literales DateTime, las partes de fecha y hora son obligatorias. No hay valores predeterminados.  
  
 Ejemplo:  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|25.12.06 01:01:00|  
  
### <a name="integer"></a>Entero  

 Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).  
  
 Ejemplo:  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>Otros  

 Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`. Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.  
  
## <a name="type-constructors"></a>Constructores de tipos  
  
### <a name="row"></a>ROW  

 La [fila](row-entity-sql.md) construye un valor anónimo, con tipo estructural (registro) como en:`ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Ejemplo:  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 Salida:  
  
|ProductID|Nombre|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  

 Las construcciones de conjuntos [MultiSet](multiset-entity-sql.md) , como:  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 Ejemplo:  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Salida:  
  
|ProductID|Nombre|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Object  

 El [constructor de tipo con nombre](named-type-constructor-entity-sql.md) crea objetos definidos por el usuario (con nombre), como `person("abc", 12)` .  
  
 Ejemplo:  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 Salida:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>Referencias  
  
### <a name="ref"></a>REF  

 [Ref](ref-entity-sql.md) crea una referencia a una instancia de tipo de entidad. Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad. Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.  
  
 Ejemplo:  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Salida:  
  
|Value|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  

 [Deref](deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación. Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Ejemplo:  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Salida:  
  
|Value|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF y KEY  

 [CREATEREF](createref-entity-sql.md) crea una referencia que pasa una clave. La [clave](key-entity-sql.md) extrae la parte de la clave de una expresión con referencia de tipo.  
  
 Ejemplo:  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 Salida:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## <a name="functions"></a>Functions  
  
### <a name="canonical"></a>Canonical  

 El espacio de nombres para [las funciones canónicas](canonical-functions.md) es EDM, como en `Edm.Length("string")` . No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica. Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.  
  
 Ejemplo:  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 Salida:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### <a name="microsoft-provider-specific"></a>Específicas de proveedores de Microsoft  

 [Las funciones específicas del proveedor de Microsoft](../sqlclient-for-ef-functions.md) se encuentran en el `SqlServer` espacio de nombres.  
  
 Ejemplo:  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 Salida:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## <a name="namespaces"></a>Espacios de nombres  

 El [uso](using-entity-sql.md) de especifica espacios de nombres utilizados en una expresión de consulta.  
  
 Ejemplo:  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Paginación  

 La paginación se puede expresar declarando una cláusula [SKIP](skip-entity-sql.md) y [Limit](limit-entity-sql.md) en la cláusula [order by](order-by-entity-sql.md) .  
  
 Ejemplo:  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Salida:  
  
|ID|Nombre|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Agrupar  

 La [agrupación por](group-by-entity-sql.md) especifica los grupos en los que se van a colocar los objetos devueltos por una expresión de consulta ([Select](select-entity-sql.md)).  
  
 Ejemplo:  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Salida:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>Navegación  

 El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final). [Navigate](navigate-entity-sql.md) toma el tipo de relación calificado como \<namespace> . \<relationship type name> . Navigate devuelve Ref \<T> si la cardinalidad del extremo final es 1. Si la cardinalidad del extremo final es n, se devolverá la colección<> de referencia \<T> .  
  
 Ejemplo:  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 Salida:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## <a name="select-value-and-select"></a>SELECT VALUE y SELECT  
  
### <a name="select-value"></a>SELECT VALUE  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas. Solo se puede especificar un elemento en una cláusula SELECT VALUE. Cuando se utiliza este tipo de cláusula, no se crea ningún contenedor de filas en torno a los elementos de la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a` .  
  
 Ejemplo:  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 Salida:  
  
|Nombre|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] también proporciona el constructor de filas para crear filas arbitrarias. SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.  
  
 Ejemplo:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|Nombre|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>EXPRESIÓN CASE  

 La [expresión Case](case-entity-sql.md) evalúa un conjunto de Expresiones booleanas para determinar el resultado.  
  
 Ejemplo:  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Salida:  
  
|Value|  
|-----------|  
|true|  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](entity-sql-reference.md)
- [Información general sobre Entity SQL](entity-sql-overview.md)
