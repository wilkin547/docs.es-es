---
title: Preguntas más frecuentes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 252ed666-0679-4eea-b71b-2f14117ef443
ms.openlocfilehash: 68d4215129cf4481beb2d8561c1569b3049a287e
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610581"
---
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes
Las siguientes secciones dan respuesta a algunos problemas comunes que podría encontrar al implementar [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].  
  
 Otros problemas se tratan en [Troubleshooting](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md).  
  
## <a name="cannot-connect"></a>No se puede conectar  
 P. No puedo conectarme a mi base de datos.  
  
 R. Asegúrese de que la cadena de conexión es correcta y que se está ejecutando la instancia de SQL Server. También tenga en cuenta que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] requiere que el protocolo Canalizaciones con nombre esté habilitado. Para obtener más información, consulte [aprender con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
## <a name="changes-to-database-lost"></a>La base de datos pierde los cambios realizados  
 P. Realicé un cambio en los datos de la base de datos, pero, cuando volví a ejecutar mi aplicación, el cambio ya no estaba.  
  
 R. Asegúrese de que llama a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> para guardar los resultados en la base de datos.  
  
## <a name="database-connection-open-how-long"></a>Conexión de base de datos: ¿Durante cuánto tiempo desea abrir?  
 P. ¿Cuánto tiempo permanece abierta mi conexión a una base de datos?  
  
 R. Normalmente, una conexión permanece abierta hasta que se utilizan los resultados de la consulta. Si espera que los resultados tarden tiempo en procesarse, y no se opone a que se almacenen en memoria caché, aplique <xref:System.Linq.Enumerable.ToList%2A> a la consulta. En escenarios habituales donde cada objeto se procesa solo una vez, el modelo de transmisión por secuencias es superior tanto en `DataReader` como en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 Los detalles exactos de uso de la conexión dependen de lo siguiente:  
  
- Estado de la conexión si el <xref:System.Data.Linq.DataContext> se construye con un objeto de conexión.  
  
- Opciones de la cadena de conexión; por ejemplo, habilitar conjuntos de resultados activos múltiples (MARS). Para obtener más información, consulte [Conjuntos de resultados activos múltiples (MARS)](../../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md).  
  
## <a name="updating-without-querying"></a>Actualizaciones sin consultas  
 P. ¿Puedo actualizar los datos de la tabla sin consultar primero la base de datos?  
  
 R. Aunque [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no posee comandos de actualización basados en conjuntos, puede utilizar cualquiera de las técnicas siguientes para actualizar sin consultar primero:  
  
- Utilice <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> para enviar código SQL.  
  
- Cree una nueva instancia del objeto e inicialice todos los valores (campos) actuales que afectan a la actualización. A continuación, adjunte el objeto al <xref:System.Data.Linq.DataContext> utilizando <xref:System.Data.Linq.Table%601.Attach%2A> y modifique el campo que desee cambiar.  
  
## <a name="unexpected-query-results"></a>Resultados inesperados en la consulta  
 P. Mi consulta devuelve resultados inesperados. ¿Cómo puedo inspeccionar lo que está ocurriendo?  
  
 R. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona varias herramientas para inspeccionar el código SQL que genera. Una de las más importantes es <xref:System.Data.Linq.DataContext.Log%2A>. Para obtener más información, consulte [compatibilidad con depuración](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md).  
  
## <a name="unexpected-stored-procedure-results"></a>Resultados inesperados del procedimiento almacenado  
 P. Tengo un procedimiento almacenado cuyo valor devuelto se calcula mediante `MAX()`. Cuando arrastro el procedimiento almacenado hasta la superficie de [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)], el valor devuelto no es correcto.  
  
 R. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proporciona dos maneras de devolver los valores generados por la base de datos a través de procedimientos almacenados:  
  
- Asignando un nombre al resultado de salida.  
  
- Especificando explícitamente un parámetro de salida.  
  
 El siguiente es un ejemplo de resultado incorrecto. Dado que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no puede asignar los resultados, siempre devuelve 0:  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select max(i) from t where name like 'hello'`  
  
 `end`  
  
 El siguiente es un ejemplo de resultado correcto que utiliza un parámetro de salida:  
  
 `create procedure proc2`  
  
 `@result int OUTPUT`  
  
 `as`  
  
 `select @result = MAX(i) from t where name like 'hello'`  
  
 `go`  
  
 El siguiente es un ejemplo de resultado correcto que asigna un nombre al resultado de salida:  
  
 `create procedure proc2`  
  
 `as`  
  
 `begin`  
  
 `select nax(i) AS MaxResult from t where name like 'hello'`  
  
 `end`  
  
 Para obtener más información, consulte [personalizar operaciones utilizando procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md).  
  
## <a name="serialization-errors"></a>Errores de serialización  
 P. Cuando intento serializar, obtengo el siguiente error: "Escriba... 'System.Data.Linq.ChangeTracker+StandardChangeTracker' no está marcado como serializable."  
  
 R. La generación de código en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite serialización <xref:System.Runtime.Serialization.DataContractSerializer>. No admite <xref:System.Xml.Serialization.XmlSerializer> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>. Para obtener más información, vea [Serialización](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md).  
  
## <a name="multiple-dbml-files"></a>Múltiples archivos DBML  
 P. Cuando tengo varios archivos DBML que comparten algunas tablas, obtengo un error del compilador.  
  
 R. Establecer el **contexto Namespace** y **Namespace Entity** propiedades desde el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] en un valor distinto para cada archivo DBML. Este enfoque elimina la colisión entre nombres o espacios de nombres.  
  
## <a name="avoiding-explicit-setting-of-database-generated-values-on-insert-or-update"></a>Evitar el establecimiento explícito de valores generados por la base de datos al insertar o actualizar  
 P. Tengo una tabla de base de datos con una columna `DateCreated` que tiene como valor predeterminado `Getdate()` de SQL. Cuando intento insertar un nuevo registro utilizando [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], el valor queda establecido en `NULL`. Lo que esperaba es que tomara el valor predeterminado de la base de datos.  
  
 R. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] administra automáticamente esta situación para la identidad (incremento automático) y rowguidcol (GUID generado por base de datos) y para las columnas con marca de tiempo. En otros casos, debería establecer manualmente <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> = `true` y <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> = <xref:System.Data.Linq.Mapping.AutoSync.Always> / <xref:System.Data.Linq.Mapping.AutoSync.OnInsert> / <xref:System.Data.Linq.Mapping.AutoSync.OnUpdate> propiedades.  
  
## <a name="multiple-dataloadoptions"></a>Múltiples DataLoadOptions  
 P. ¿Puedo especificar opciones de carga adicionales sin sobrescribir la primera?  
  
 R. Sí. La primera no se sobrescribe, como se muestra en el ejemplo siguiente:  
  
```vb  
Dim dlo As New DataLoadOptions()  
dlo.LoadWith(Of Order)(Function(o As Order) o.Customer)  
dlo.LoadWith(Of Order)(Function(o As Order) o.OrderDetails)  
```  
  
```csharp  
DataLoadOptions dlo = new DataLoadOptions();  
dlo.LoadWith<Order>(o => o.Customer);  
dlo.LoadWith<Order>(o => o.OrderDetails);  
```  
  
## <a name="errors-using-sql-compact-35"></a>Errores en el uso de SQL Compact 3.5  
 P. Obtengo un error cuando arrastro tablas fuera de una base de datos de SQL Server Compact 3.5.  
  
 R. El [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] no admite SQL Server Compact 3.5, aunque el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime realiza. En esta situación, debe crear sus propias clases de entidad y agregar los atributos adecuados.  
  
## <a name="errors-in-inheritance-relationships"></a>Errores en relaciones de herencia  
 P. Utilizo la herramienta de herencia incluida en el cuadro de herramientas del [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para conectar dos entidades, pero obtengo errores.  
  
 R. Crear una relación no es suficiente. Debe proporcionar información tal como la columna de discriminador, el valor de discriminador de la clase base y el valor de discriminador de la clase derivada.  
  
## <a name="provider-model"></a>Modelo de proveedor  
 P. ¿Existe un modelo de proveedor público disponible?  
  
 R. No existe ningún modelo de proveedor público disponible. En este momento, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solo es compatible con SQL Server y SQL Server Compact 3.5.  
  
## <a name="sql-injection-attacks"></a>Ataques mediante inserción de SQL  
 P. ¿Cómo se protege [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] de ataques de inyección de código SQL?  
  
 R. La inyección de código SQL ha sido un riesgo significativo para las consultas SQL tradicionales formadas mediante concatenación de los datos proporcionados por el usuario. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] evita esa inyección de código mediante el uso de <xref:System.Data.SqlClient.SqlParameter> en las consultas. Los datos proporcionados por el usuario se convierten en valores de parámetro. Este enfoque impide que se utilicen comandos malintencionados en los datos proporcionados por el cliente.  
  
## <a name="changing-read-only-flag-in-dbml-files"></a>Cambiar la marca de solo lectura en archivos DBML  
 P. ¿Cómo elimino los establecedores procedentes de algunas propiedades cuando creo un modelo de objetos a partir de un archivo DBML?  
  
 R. Siga estos pasos para este escenario avanzado:  
  
1. En el archivo .dbml, modifique la propiedad cambiando la marca <xref:System.Data.Linq.ITable.IsReadOnly%2A> a `True`.  
  
2. Agregue una clase parcial. Cree un constructor con parámetros para los miembros de solo lectura.  
  
3. Revise el valor predeterminado de <xref:System.Data.Linq.Mapping.UpdateCheck> (<xref:System.Data.Linq.Mapping.UpdateCheck.Never>) para determinar si ése es el valor correcto para su aplicación.  
  
    > [!CAUTION]
    >  Si usas el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] en Visual Studio, se pueden sobrescribir los cambios.  
  
## <a name="aptca"></a>APTCA  
 P. ¿Está System.Data.Linq marcado para que el código de confianza parcial pueda utilizarlo?  
  
 R. Sí, el ensamblado System.Data.Linq.dll se encuentra entre los ensamblados de .NET Framework marcados con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo. Sin este marcado, los ensamblados de .NET Framework están diseñados para su uso sólo por código de plena confianza.  
  
 El principal escenario de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para permitir parcialmente es permitir que los llamadores de confianza la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ensamblado necesario acceder desde las aplicaciones Web, donde el *confianza* configuración es Medium.  
  
## <a name="mapping-data-from-multiple-tables"></a>Asignación de datos procedentes de varias tablas  
 P. Los datos de mi entidad proceden de varias tablas. ¿Cómo realizo la asignación?  
  
 R. Puede crear una vista en una base de datos y asignar la entidad a la vista. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera el mismo código SQL para vistas que para tablas.  
  
> [!NOTE]
>  El uso de vistas en este escenario presenta limitaciones. Este enfoque funciona de forma más segura cuando las operaciones realizadas sobre <xref:System.Data.Linq.Table%601> se admiten en la vista subyacente. Solo usted puede saber qué operaciones son las deseadas. Por ejemplo, la mayoría de las aplicaciones es de solo lectura, y otro número considerable realiza `Create` / `Update` / `Delete` las operaciones de solo mediante procedimientos almacenan en las vistas.  
  
## <a name="connection-pooling"></a>Agrupación de conexiones  
 P. ¿Existe una construcción que pueda ayudar al agrupamiento de <xref:System.Data.Linq.DataContext>?  
  
 R. No intente reutilizar instancias de <xref:System.Data.Linq.DataContext>. Cada <xref:System.Data.Linq.DataContext> mantiene el estado (incluida una caché de identidad) para una sesión de edición o consulta particular. Para obtener nuevas instancias según el estado actual de la base de datos, utilice un nuevo <xref:System.Data.Linq.DataContext>.  
  
 Todavía puede usar la agrupación de conexiones ADO.NET subyacente. Para obtener más información, vea [Agrupación de conexiones de SQL Server (ADO.NET)](../../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
## <a name="second-datacontext-is-not-updated"></a>El segundo DataContext no resulta actualizado  
 P. Utilizo una instancia de <xref:System.Data.Linq.DataContext> para almacenar valores en la base de datos. Sin embargo, un segundo <xref:System.Data.Linq.DataContext> en la misma base de datos no refleja los valores actualizados. La segunda instancia de <xref:System.Data.Linq.DataContext> parece devolver valores almacenados en memoria caché.  
  
 R. Este comportamiento está diseñado así. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] continúa devolviendo los mismos valores o instancias que aparecen en la primera instancia. Cuando se realizan actualizaciones, se utiliza simultaneidad optimista. Los datos originales se utilizan para realizar una comprobación contra el estado de la base de datos actual a fin de comprobar que, de hecho, permanecen sin modificar. Si han cambiado, se produce un conflicto, y su aplicación deberá resolverlo. Una opción para su aplicación es restablecer el estado original al estado actual de la base de datos e intentar de nuevo la actualización. Para obtener más información, vea [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
 También puede establecer <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> como falso, lo cual desactiva el almacenamiento en memoria caché y el seguimiento de cambios. A continuación, puede recuperar los últimos valores cada vez que realiza una consulta.  
  
## <a name="cannot-call-submitchanges-in-read-only-mode"></a>No se puede llamar a SubmitChanges en modo de solo lectura  
 P. Cuando intento llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A> en modo de solo lectura, obtengo un error.  
  
 R. El modo de solo lectura desactiva la capacidad del contexto de realizar seguimiento de cambios.  
  
## <a name="see-also"></a>Vea también

- [Referencia](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [Solución de problemas](../../../../../../docs/framework/data/adonet/sql/linq/troubleshooting.md)
- [Seguridad de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)
