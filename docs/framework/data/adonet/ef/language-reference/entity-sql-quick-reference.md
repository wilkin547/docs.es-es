---
title: Referencia rápida de Entity SQL
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: b4e3eaf8abd82b63fa2663b47f878ecfa9584897
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207076"
---
# <a name="entity-sql-quick-reference"></a>Referencia rápida de Entity SQL
Este tema proporciona una referencia rápida a las consultas de [!INCLUDE[esql](../../../../../../includes/esql-md.md)]. Las consultas en este tema se basan en el modelo AdventureWorks Sales.  
  
## <a name="literals"></a>Literales  
  
### <a name="string"></a>String  
 Hay literales de cadenas de caracteres Unicode y no Unicode. Las cadenas Unicode van precedidas de N. Por ejemplo, `N'hello'`.  
  
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
  
### <a name="datetime"></a>DateTime  
 En los literales DateTime, las partes de fecha y hora son obligatorias. No hay valores predeterminados.  
  
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
  
### <a name="integer"></a>Integer  
 Los literales enteros pueden ser de tipo Int32 (123), UInt32 (123U), Int64 (123L) y UInt64 (123UL).  
  
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
  
### <a name="other"></a>Otros  
 Los literales Other admitidos por [!INCLUDE[esql](../../../../../../includes/esql-md.md)] son Guid, Binary, Float/Double, Decimal y `null`. Los literales NULL en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] se consideran compatibles con todos los demás tipos del modelo conceptual.  
  
## <a name="type-constructors"></a>Constructores de tipos  
  
### <a name="row"></a>ROW  
 [FILA](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md) crea un valor (registro) anónimo, escrito estructuralmente como en: `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Ejemplo:  
  
```  
SELECT VALUE row (product.ProductID as ProductID, product.Name   
    as ProductName) FROM AdventureWorksEntities.Product AS product  
```  
  
 Resultado:  
  
|ProductID|Name|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  
 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md) crea colecciones, como:  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 Ejemplo:  
  
```  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Resultado:  
  
|ProductID|Name|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Object  
 [Llamada de Constructor de tipo](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md) construye los objetos definidos por el usuario (nombre), como `person("abc", 12)`.  
  
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
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>Referencias  
  
### <a name="ref"></a>REF  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md) crea una referencia a una instancia del tipo de entidad. Por ejemplo, la consulta siguiente devuelve referencias a cada entidad Order en el conjunto de entidades Orders:  
  
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
  
 En el ejemplo siguiente se usa el operador de extracción de propiedades (.) para tener acceso a una propiedad de una entidad. Cuando se utiliza el operador de extracción de propiedades, la referencia se desreferencia automáticamente.  
  
 Ejemplo:  
  
```  
SELECT VALUE REF(p).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md) desreferencia un valor de referencia y genera el resultado de dicha desreferenciación. Por ejemplo, la consulta siguiente genera las entidades Order para cada entidad Order en el conjunto de entidades Orders: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Ejemplo:  
  
```  
SELECT VALUE DEREF(REF(p)).Name FROM   
    AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF y KEY  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md) crea una referencia que pasa una clave. [CLAVE](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md) extrae la parte de una expresión con referencia de tipo de clave.  
  
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
  
## <a name="functions"></a>Funciones  
  
### <a name="canonical"></a>Canónicas  
 El espacio de nombres [funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md) es Edm, como en `Edm.Length("string")`. No es necesario especificar el espacio de nombres a no ser que se importe otro espacio de nombres que contenga una función con el mismo nombre que una función canónica. Si dos espacios de nombres tienen la misma función, el usuario debe especificar el nombre completo.  
  
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
  
### <a name="microsoft-provider-specific"></a>Específicas de proveedores de Microsoft  
 [Funciones específicas del proveedor de Microsoft](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md) están en el `SqlServer` espacio de nombres.  
  
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
  
## <a name="namespaces"></a>Espacios de nombres  
 [USO de](../../../../../../docs/framework/data/adonet/ef/language-reference/using-entity-sql.md) especifica los espacios de nombres utilizados en una expresión de consulta.  
  
 Ejemplo:  
  
```  
using SqlServer; LOWER('AA');  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Paginación  
 Paginación se puede expresar declarando un [omitir](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) y [límite](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) subcláusulas a la [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) cláusula.  
  
 Ejemplo:  
  
```  
SELECT c.ContactID as ID, c.LastName as Name FROM   
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Resultado:  
  
|ID|Name|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Agrupar  
 [GROUPING BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) especifica los grupos en los objetos devueltos por una consulta ([seleccione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)) expresión que se van a colocarse.  
  
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
  
## <a name="navigation"></a>Navegación  
 El operador de navegación por relaciones permite navegar por la relación de un tipo de entidad (extremo inicial) a otro (extremo final). [NAVIGATE](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) toma el tipo de relación calificado como \<espacio de nombres >.\< nombre de tipo de relación >. Navegue devuelve Ref\<T > Si la cardinalidad del extremo final es 1. Si la cardinalidad del extremo final es n, la colección < Ref\<T >> se devolverá.  
  
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
  
## <a name="select-value-and-select"></a>SELECT VALUE y SELECT  
  
### <a name="select-value"></a>SELECT VALUE  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] proporciona la cláusula SELECT VALUE para omitir la creación de filas implícitas. Solo se puede especificar un elemento en una cláusula SELECT VALUE. Cuando se usa una cláusula de ese tipo, se crea ningún contenedor de filas en torno a los elementos en la cláusula SELECT y se puede generar una colección de la forma deseada, por ejemplo: `SELECT VALUE a`.  
  
 Ejemplo:  
  
```  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product as p  
```  
  
 Resultado:  
  
|Name|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] También proporciona el constructor de filas para crear filas arbitrarias. SELECT toma uno o más elementos en la proyección y devuelve un registro de datos con campos, por ejemplo: `SELECT a, b, c`.  
  
 Ejemplo:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Output:  
  
|Name|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>EXPRESIÓN CASE  
 El [caso expresión](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md) evalúa un conjunto de expresiones booleanas para determinar el resultado.  
  
 Ejemplo:  
  
```  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Resultado:  
  
|Valor|  
|-----------|  
|true|  
  
## <a name="see-also"></a>Vea también

- [Referencia de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Información general sobre Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
