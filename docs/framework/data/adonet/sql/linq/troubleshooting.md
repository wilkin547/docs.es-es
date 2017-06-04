---
title: "Soluci&#243;n de problemas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Soluci&#243;n de problemas
La siguiente información expone algunos problemas que podría encontrar en sus aplicaciones de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona sugerencias para evitar o reducir el efecto de estos problemas.  
  
 Otros problemas se tratan en [Preguntas más frecuentes](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md).  
  
## Operadores de consulta estándar no admitidos  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite todos los métodos de operador de consulta estándar \(por ejemplo, <xref:System.Linq.Enumerable.ElementAt%2A>\).  Como resultado, aunque los proyectos se compilen correctamente, pueden producir errores en tiempo de ejecución.  Para obtener más información, consulta [Conversión de operadores de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
## Problemas de memoria  
 Si una consulta utiliza una colección que reside en memoria y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<xref:System.Data.Linq.Table%601>, la consulta se podría ejecutar en memoria, dependiendo del orden en el que se especifiquen las dos colecciones.  Si la consulta se debe ejecutar en memoria, entonces es necesario recuperar los datos de la tabla de la base de datos.  
  
 Este enfoque es ineficiente y podría provocar un uso excesivo del procesador y de la memoria.  Intente evitar esas consultas multidominio.  
  
## Nombres de archivo y SQLMetal  
 Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada.  No se admite la inclusión del nombre de archivo en la cadena de conexión \(mediante la opción **\/conn**\).  Para obtener más información, consulta [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Proyectos de biblioteca de clases  
 El [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] crea una cadena de conexión en el archivo `app.config` del proyecto.  En proyectos de biblioteca de clases, el archivo `app.config` no se utiliza.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza la cadena de conexión proporcionada en los archivos en tiempo de diseño.  Al cambiar el valor en `app.config`, la base de datos a la que se conecta su aplicación no cambia.  
  
## Eliminación en cascada  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite ni reconoce las operaciones de eliminación en cascada.  Si desea eliminar una fila de una tabla que tiene restringidas las eliminaciones, deberá hacerlo mediante una de las siguientes opciones:  
  
-   Establezca la regla `ON DELETE CASCADE` en la restricción de clave externa de la base de datos.  
  
-   Utilice su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario.  
  
 En caso contrario, se producirá una excepción <xref:System.Data.SqlClient.SqlException>.  
  
 Para obtener más información, consulta [Cómo: Eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
## Expresión que no se puede consultar  
 Si obtiene el error "No se puede consultar una expresión de tipo \[expresión\]. Compruebe que no falta ninguna referencia de ensamblado", asegúrese de lo siguiente:  
  
-   Su aplicación va destinada a [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)].  
  
-   Tiene una referencia a `System.Core.dll` y `System.Data.Linq.dll`.  
  
-   Tiene una directiva `Imports` \([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) o `using` \(C\#\) para <xref:System.Linq> y <xref:System.Data.Linq>.  
  
## DuplicateKeyException  
 Durante la depuración de un proyecto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se podrían recorrer las relaciones de una entidad.  Al hacer esto, esos elementos se introducen en la caché, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se da cuenta de su presencia.  Si, a continuación, intenta ejecutar <xref:System.Data.Linq.Table%601.Attach%2A> o <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> o un método similar que genere varias filas con que presenten la misma clave, se producirá la excepción <xref:System.Data.Linq.DuplicateKeyException>.  
  
## Excepciones de concatenación de cadenas  
 No se admite la concatenación sobre operandos asignados a `[n]text` y otros `[n][var]char`.  Se produce una excepción para la concatenación de cadenas asignadas a los dos conjuntos diferentes de tipos.  Para obtener más información, consulta [System.String \(Métodos\)](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md).  
  
## Omitir y aceptar excepciones en SQL Server 2000  
 Debe usar miembros de identidad \(<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>\) cuando utilice <xref:System.Linq.Queryable.Take%2A> o <xref:System.Linq.Queryable.Skip%2A> contra una base de datos de SQL Server 2000.  La consulta debe realizarse contra una sola tabla \(es decir, no una unión\), o ser una operación <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> o <xref:System.Linq.Queryable.Union%2A>, y no debe incluir una operación <xref:System.Linq.Queryable.Concat%2A>.  Para obtener más información, vea la sección de "Compatibilidad con SQL Server 2000" en [Conversión de operadores de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
 Este requisito no se aplica a [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
## GroupBy InvalidOperationException  
 Esta excepción se produce cuando un valor de columna es nulo en una consulta <xref:System.Linq.Enumerable.GroupBy%2A> que agrupa mediante una expresión `boolean`, como `group x by (Phone==@phone)`.  Dado que la expresión es `boolean`, se deduce que la clave será `boolean`, no `nullable``boolean`.  Cuando la comparación traducida genera un valor nulo \(null\), se realizará un intento de asignar un `nullable``boolean` a un `boolean`, y se producirá la excepción.  
  
 Para evitar esta situación \(suponiendo que desea tratar los valores null como falsos\), utilice un enfoque como el siguiente:  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## Método parcial OnCreated\(\)  
 Se llama al método generado `OnCreated()` cada vez que se llama al constructor de objeto, incluido el escenario en el que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] llama al constructor para realizar una copia para los valores originales.  Tenga en cuenta este comportamiento si implementa el método `OnCreated()` en su propia clase parcial.  
  
## Vea también  
 [Compatibilidad con depuración](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)   
 [Preguntas más frecuentes](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)