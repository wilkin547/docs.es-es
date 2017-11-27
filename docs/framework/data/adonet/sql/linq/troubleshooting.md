---
title: "Solución de problemas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cd4401c-b12c-4116-a421-f3dcffa65670
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c4674acd6d097eb1cb03d5dd07b0c686404d1145
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting"></a>Solución de problemas
La siguiente información expone algunos problemas que podría encontrar en sus aplicaciones de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y proporciona sugerencias para evitar o reducir el efecto de estos problemas.  
  
 Problemas adicionales se solucionarán en [Frequently Asked Questions](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md).  
  
## <a name="unsupported-standard-query-operators"></a>Operadores de consulta estándar no admitidos  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite todos los métodos de operador de consulta estándar (por ejemplo, <xref:System.Linq.Enumerable.ElementAt%2A>). Como resultado, aunque los proyectos se compilen correctamente, pueden producir errores en tiempo de ejecución. Para obtener más información, consulte [traducción de operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
## <a name="memory-issues"></a>Problemas de memoria  
 Si una consulta utiliza una colección en memoria y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Table%601>, la consulta se podría ejecutar en memoria, dependiendo del orden en que se especifican las dos colecciones. Si la consulta se debe ejecutar en memoria, entonces es necesario recuperar los datos de la tabla de la base de datos.  
  
 Este enfoque es ineficiente y podría provocar un uso excesivo del procesador y de la memoria. Intente evitar esas consultas multidominio.  
  
## <a name="file-names-and-sqlmetal"></a>Nombres de archivo y SQLMetal  
 Para especificar un nombre de archivo de entrada, agregue el nombre a la línea de comandos como archivo de entrada. No se admite la inclusión del nombre de archivo en la cadena de conexión (mediante la opción **/conn** ). Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="class-library-projects"></a>Proyectos de biblioteca de clases  
 El [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] crea una cadena de conexión en el archivo `app.config` del proyecto. En proyectos de biblioteca de clases, el archivo `app.config` no se utiliza. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] utiliza la cadena de conexión proporcionada en los archivos en tiempo de diseño. Al cambiar el valor en `app.config`, la base de datos a la que se conecta su aplicación no cambia.  
  
## <a name="cascade-delete"></a>Eliminación en cascada  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite ni reconoce las operaciones de eliminación en cascada. Si desea eliminar una fila de una tabla que tiene restringidas las eliminaciones, deberá hacerlo mediante una de las siguientes opciones:  
  
-   Establezca la regla `ON DELETE CASCADE` en la restricción de clave externa de la base de datos.  
  
-   Utilice su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario.  
  
 En caso contrario, se producirá una excepción <xref:System.Data.SqlClient.SqlException>.  
  
 Para obtener más información, consulte [Cómo: eliminar filas de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-delete-rows-from-the-database.md).  
  
## <a name="expression-not-queryable"></a>Expresión que no se puede consultar  
 Si obtiene el error "No se puede consultar una expresión de tipo [expresión]. Compruebe que no falta ninguna referencia de ensamblado", asegúrese de lo siguiente:  
  
-   Su aplicación va destinada a [!INCLUDE[compact_v35_short](../../../../../../includes/compact-v35-short-md.md)].  
  
-   Tiene una referencia a `System.Core.dll` y `System.Data.Linq.dll`.  
  
-   Tiene una directiva `Imports` ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) o `using` (C#) para <xref:System.Linq> y <xref:System.Data.Linq>.  
  
## <a name="duplicatekeyexception"></a>DuplicateKeyException  
 Durante la depuración un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto, se podrían recorrer las relaciones de una entidad. Si lo hace, sitúa estos elementos en la memoria caché, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pasa a ser consciente de su presencia. Si, a continuación, intenta ejecutar <xref:System.Data.Linq.Table%601.Attach%2A> o <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> o un método similar que genere varias filas con que presenten la misma clave, se producirá la excepción <xref:System.Data.Linq.DuplicateKeyException>.  
  
## <a name="string-concatenation-exceptions"></a>Excepciones de concatenación de cadenas  
 No se admite la concatenación sobre operandos asignados a `[n]text` y otros `[n][var]char`. Se produce una excepción para la concatenación de cadenas asignadas a los dos conjuntos diferentes de tipos. Para obtener más información, consulte [métodos System.String](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md).  
  
## <a name="skip-and-take-exceptions-in-sql-server-2000"></a>Omitir y aceptar excepciones en SQL Server 2000  
 Debe usar miembros de identidad (<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>) cuando utilice <xref:System.Linq.Queryable.Take%2A> o <xref:System.Linq.Queryable.Skip%2A> contra una base de datos de SQL Server 2000. La consulta debe realizarse contra una sola tabla (es decir, no una unión), o ser una operación <xref:System.Linq.Queryable.Distinct%2A>, <xref:System.Linq.Queryable.Except%2A>, <xref:System.Linq.Queryable.Intersect%2A> o <xref:System.Linq.Queryable.Union%2A>, y no debe incluir una operación <xref:System.Linq.Queryable.Concat%2A>. Para obtener más información, vea la sección "Compatibilidad con SQL Server 2000" en [traducción de operador de consulta estándar](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md).  
  
 Este requisito no se aplica a [!INCLUDE[sqprsqlong](../../../../../../includes/sqprsqlong-md.md)].  
  
## <a name="groupby-invalidoperationexception"></a>GroupBy InvalidOperationException  
 Esta excepción se produce cuando un valor de columna es nulo en una consulta <xref:System.Linq.Enumerable.GroupBy%2A> que agrupa mediante una expresión `boolean`, como `group x by (Phone==@phone)`. Dado que la expresión es un `boolean`, la clave se deduce como `boolean`, no `nullable``boolean`. Cuando la comparación traducida genera un valor null, se realiza un intento para asignar un `nullable``boolean` a un `boolean`, y se produce la excepción.  
  
 Para evitar esta situación (suponiendo que desea tratar los valores null como falsos), utilice un enfoque como el siguiente:  
  
 `GroupBy="(Phone != null) && (Phone=@Phone)"`  
  
## <a name="oncreated-partial-method"></a>Método parcial OnCreated()  
 Se llama al método generado `OnCreated()` cada vez que se llama al constructor de objeto, incluido el escenario en el que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] llama al constructor para realizar una copia para los valores originales. Tenga en cuenta este comportamiento si implementa el método `OnCreated()` en su propia clase parcial.  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con la depuración](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 [Preguntas más frecuentes](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)
