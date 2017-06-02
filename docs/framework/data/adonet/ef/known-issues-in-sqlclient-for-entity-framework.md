---
title: "Problemas conocidos en SqlClient para Entity Framework | Microsoft Docs"
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
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Problemas conocidos en SqlClient para Entity Framework
En esta sección se describen problemas conocidos relacionados con el proveedor de datos .NET Framework para SQL Server \(SqlClient\).  
  
## Espacios finales en funciones de cadena  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] omite los espacios finales en los valores de cadena.  Por consiguiente, al pasar espacios finales en una cadena, se pueden producir resultados imprevisibles, incluso errores.  
  
 Si ha de tener espacios finales en una cadena, debería considerar anexar un carácter de espacio en blanco al final, para que [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] no recorte la cadena.  Si no se requieren los espacios finales, se deberían recortar antes de pasarse a la canalización de la consulta.  
  
## Función RIGHT  
 Si se pasa un valor no `null` como primer argumento y se pasa 0 como segundo argumento a la función `RIGHT(nvarchar(max)`, 0`)` o `RIGHT(varchar(max)`, 0`)`, se devolverá un valor `NULL` en lugar de una cadena `empty`.  
  
## Operadores CROSS APPLY y OUTER APPLY  
 Los operadores CROSS APPLY y OUTER APPLY se incluyeron en [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  En algunos casos, la canalización de la consulta podría generar una instrucción de Transact\-SQL que contenga los operadores CROSS APPLY y\/o OUTER APPLY.  Dado que algunos proveedores back\-end, incluidas las versiones de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], no admiten estos operadores, tales consultas no se pueden ejecutar en ellos.  
  
 A continuación se ilustran escenarios típicos que podrían conducir a la presencia de los operadores CROSS APPLY y\/o OUTER APPLY en la consulta de salida:  
  
-   Una subconsulta correlacionada con paginación.  
  
-   Un `AnyElement` sobre una subconsulta correlacionada o sobre una colección generada mediante navegación.  
  
-   Consultas de LINQ que utilizan métodos de agrupación que aceptan un selector de elemento.  
  
-   Una consulta en la que se especifica explícitamente un operador CROSS APPLY u OUTER APPLY  
  
-   Una consulta que tiene una construcción DEREF sobre una construcción REF.  
  
## Operador SKIP  
 Si usa [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)], el uso de SKIP con ORDER BY en columnas sin clave puede hacer que los resultados devueltos sean incorrectos.  Se puede omitir un número superior al número especificado de filas si la columna sin clave tiene datos duplicados en ella.  Esto se debe a cómo se convierte SKIP en [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].  Por ejemplo, en la consulta siguiente se pueden omitir más de cinco filas si `E.NonKeyColumn` tiene valores duplicados:  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## Cuál es la versión correcta de SQL Server  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] destina la consulta [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] según la versión de SQL Server que se especifica en el atributo `ProviderManifestToken` del elemento Schema del archivo del modelo de almacenamiento \(.ssdl\).  Esta versión podría diferir de la versión de SQL Server real al que está conectado.  Por ejemplo, si usa SQL Server 2005, pero el atributo `ProviderManifestToken` está establecido en 2008, la consulta de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] generada podría no ejecutarse en el servidor. Por ejemplo, una consulta que use los nuevos tipos de fecha y hora que se incluyeron en SQL Server 2008 no se ejecutará en las versiones anteriores de SQL Server.  Si usa SQL Server 2005, pero el atributo `ProviderManifestToken` está establecido en 2000, la consulta de [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] generada se podría optimizar menos o se podría obtener una excepción que indicara que la consulta no se admite.  Para obtener más información, vea la sección Operadores CROSS APPLY y OUTER APPLY, anteriormente en este tema.  
  
 Ciertos comportamientos de las bases de datos dependen del nivel de compatibilidad establecida en la base de datos.  Si el atributo `ProviderManifestToken` está establecido en 2005 y la versión de SQL Server es 2005, pero el nivel de compatibilidad de una base de datos está establecido en "80" \(SQL Server 2000\), el código [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] generado estará destinado a SQL Server 2005, pero podría no ejecutarse tal y como se esperaba debido a la configuración del nivel de compatibilidad.  Por ejemplo, podría perder la información de los pedidos si un nombre de columna de la lista ORDER BY coincide con un nombre de columna en el selector.  
  
## Consultas anidadas en proyección  
 Las consultas anidadas en una cláusula de proyección se podrían traducir en consultas de producto cartesiano en el servidor.  Esto puede hacer que la tabla TempDB crezca demasiado en algunos servidores back\-end, incluido SLQ Server.  Esto puede hacer que disminuya el rendimiento del servidor.  
  
 El siguiente es un ejemplo de una consulta anidada en una cláusula de proyección:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## Valores de identidad de GUID generados por el servidor  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es compatible con los valores de identidad de tipo GUID generados por el servidor, pero el proveedor debe admitir a su vez la devolución de dichos valores después de la inserción de una fila.  A partir de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2005, es posible devolver el tipo GUID generado por el servidor en una base de datos de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] mediante la [cláusula OUTPUT](http://go.microsoft.com/fwlink/?LinkId=169400).  
  
## Vea también  
 [SqlClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)   
 [Problemas conocidos y consideraciones en LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)