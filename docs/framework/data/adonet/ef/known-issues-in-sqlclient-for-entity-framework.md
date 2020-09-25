---
title: Problemas conocidos en SqlClient para Entity Framework
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: 707c749e4dff5d1bbc8d372632aae502092db060
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198111"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Problemas conocidos en SqlClient para Entity Framework

En esta sección se describen problemas conocidos relacionados con el proveedor de datos .NET Framework para SQL Server (SqlClient).  
  
## <a name="trailing-spaces-in-string-functions"></a>Espacios finales en funciones de cadena  

 SQL Server omite los espacios finales en los valores de cadena. Por consiguiente, al pasar espacios finales en una cadena, se pueden producir resultados imprevisibles, incluso errores.  
  
 Si tiene que tener espacios finales en la cadena, considere la posibilidad de anexar un carácter de espacio en blanco al final, de modo que SQL Server no recorte la cadena. Si no se requieren los espacios finales, se deberían recortar antes de pasarse a la canalización de la consulta.  
  
## <a name="right-function"></a>Función RIGHT  

 Si se pasa un valor no `null` como primer argumento y se pasa 0 como segundo argumento a la función `RIGHT(nvarchar(max)`, 0`)` o `RIGHT(varchar(max)`, 0`)`, se devolverá un valor `NULL` en lugar de una cadena `empty`.  
  
## <a name="cross-and-outer-apply-operators"></a>Operadores CROSS APPLY y OUTER APPLY  

 Los operadores CROSS APPLY y OUTER APPLY se introdujeron en SQL Server 2005. En algunos casos, la canalización de la consulta podría generar una instrucción de Transact-SQL que contenga los operadores CROSS APPLY y/o OUTER APPLY. Dado que algunos proveedores de back-end, incluidas las versiones de SQL Server anteriores a SQL Server 2005, no admiten estos operadores, tales consultas no se pueden ejecutar en estos proveedores de back-end.  
  
 A continuación se ilustran escenarios típicos que podrían conducir a la presencia de los operadores CROSS APPLY y/o OUTER APPLY en la consulta de salida:  
  
- Una subconsulta correlacionada con paginación.  
  
- Un `AnyElement` sobre una subconsulta correlacionada o sobre una colección generada mediante navegación.  
  
- Consultas de LINQ que utilizan métodos de agrupación que aceptan un selector de elemento.  
  
- Una consulta en la que se especifica explícitamente un operador CROSS APPLY u OUTER APPLY  
  
- Una consulta que tiene una construcción DEREF sobre una construcción REF.  
  
## <a name="skip-operator"></a>Operador SKIP  

 Si usa SQL Server 2000, el uso de SKIP con ORDER BY en columnas que no son de clave puede devolver resultados incorrectos. Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella. Esto se debe a la forma en que se traduce SKIP para SQL Server 2000. Por ejemplo, en la consulta siguiente, se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:  
  
```sql  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Cuál es la versión correcta de SQL Server  

 La Entity Framework tiene como destino la consulta Transact-SQL basada en la versión SQL Server que se especifica en el `ProviderManifestToken` atributo del elemento Schema en el archivo de modelo de almacenamiento (. SSDL). Esta versión podría diferir de la versión de SQL Server real al que está conectado. Por ejemplo, si utiliza SQL Server 2005, pero el `ProviderManifestToken` atributo está establecido en 2008, la consulta Transact-SQL generada podría no ejecutarse en el servidor. Por ejemplo, una consulta que use los nuevos tipos de fecha y hora que se incluyeron en SQL Server 2008 no se ejecutará en las versiones anteriores de SQL Server. Si utiliza SQL Server 2005, pero el `ProviderManifestToken` atributo está establecido en 2000, la consulta Transact-SQL generada podría estar menos optimizada, o podría obtener una excepción que indica que no se admite la consulta. Para obtener más información, vea la sección Operadores CROSS APPLY y OUTER APPLY, anteriormente en este tema.  
  
 Ciertos comportamientos de las bases de datos dependen del nivel de compatibilidad establecida en la base de datos. Si el `ProviderManifestToken` atributo se establece en 2005 y la versión SQL Server es 2005, pero el nivel de compatibilidad de una base de datos se establece en "80" (SQL Server 2000), el valor de Transact-SQL generado será SQL Server 2005, pero es posible que no se ejecute según lo esperado debido a la configuración del nivel de compatibilidad. Por ejemplo, podría perder la información de los pedidos si un nombre de columna de la lista ORDER BY coincide con un nombre de columna en el selector.  
  
## <a name="nested-queries-in-projection"></a>Consultas anidadas en proyección  

 Las consultas anidadas en una cláusula de proyección se podrían traducir en consultas de producto cartesiano en el servidor. En algunos servidores back-end, incluido SQL Server, esto puede hacer que la tabla TempDB sea bastante grande. Esto puede hacer que disminuya el rendimiento del servidor.  
  
 El siguiente es un ejemplo de una consulta anidada en una cláusula de proyección:  
  
```sql  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Valores de identidad de GUID generados por el servidor  

 El Entity Framework admite valores de identidad de tipo GUID generados por el servidor, pero el proveedor debe admitir que se devuelva el valor de identidad generado por el servidor después de insertar una fila. A partir de SQL Server 2005, puede devolver el tipo GUID generado por el servidor en una base de datos SQL Server mediante la [cláusula OUTPUT](/sql/t-sql/queries/output-clause-transact-sql).
  
## <a name="see-also"></a>Consulte también

- [SqlClient para Entity Framework](sqlclient-for-the-entity-framework.md)
- [Problemas conocidos y consideraciones en LINQ to Entities](./language-reference/known-issues-and-considerations-in-linq-to-entities.md)
