---
title: "Aislamiento de instant&#225;neas en SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43ae5dd3-50f5-43a8-8d01-e37a61664176
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Aislamiento de instant&#225;neas en SQL Server
El aislamiento de instantánea mejora la simultaneidad para las aplicaciones OLTP.  
  
## Descripción del aislamiento de instantáneas y la versión de fila  
 Una vez habilitado el aislamiento de instantáneas, las versiones de filas actualizadas de cada transacción se mantienen en **tempdb**.  Cada transacción se identifica con un número único de secuencia de transacción, y estos números únicos se registran para cada versión de fila.  La transacción trabaja con las versiones de filas más recientes que tienen un número de secuencia anterior al número de secuencia de la transacción,   y omite las versiones de filas más nuevas creadas con posterioridad a su comienzo.  
  
 El término "instantánea" refleja el hecho de que todas las consultas de la transacción ven la misma versión, o instantánea, de la base de datos, en función del estado de ésta en el momento en que comienza la transacción.  En una transacción de instantánea no se adquieren bloqueos en las filas o las páginas de datos subyacentes, lo que permite que se ejecuten otras transacciones sin que una transacción anterior sin completarse las bloquee.  Las transacciones que modifican datos no bloquean a las que los leen, y éstas no bloquean a las que los escriben, como normalmente sucedería con el nivel de aislamiento predeterminado READ COMMITTED de SQL Server.  Este comportamiento de no bloqueo también reduce de forma significativa la probabilidad de interbloqueo en transacciones complejas.  
  
 El aislamiento de instantáneas emplea un modelo de simultaneidad optimista.  Si una transacción de instantánea intenta confirmar modificaciones en los datos que han cambiado desde su comienzo, se revertirá y se producirá un error.  Para evitarlo, utilice las sugerencias UPDLOCK de las instrucciones SELECT para tener acceso a los datos que se van a modificar.  Para obtener más información, vea "Sugerencias de bloqueo" en los Libros en pantalla de SQL Server.  
  
 Para habilitar el aislamiento de instantáneas, establezca la opción de base de datos ALLOW\_SNAPSHOT\_ISOLATION en ON antes de utilizarla en las transacciones.  De esta forma se activa el mecanismo para almacenar versiones de filas en la base de datos temporal \(**tempdb**\).  Deberá habilitar el aislamiento de instantáneas en todas las bases de datos que lo utilicen con la instrucción ALTER DATABASE de Transact\-SQL.  En este sentido, el aislamiento de instantáneas se diferencia de los niveles de aislamiento tradicionales de READ COMMITTED, REPEATABLE READ, SERIALIZABLE y READ UNCOMMITTED, que no necesitan configuración.  Las siguientes instrucciones activan el aislamiento de instantáneas y sustituyen el comportamiento predeterminado READ COMMITTED por SNAPSHOT:  
  
```  
ALTER DATABASE MyDatabase  
SET ALLOW_SNAPSHOT_ISOLATION ON  
  
ALTER DATABASE MyDatabase  
SET READ_COMMITTED_SNAPSHOT ON  
```  
  
 Al establecer la opción READ\_COMMITTED\_SNAPSHOT en ON, es posible tener acceso a las filas con versión con el nivel de aislamiento predeterminado READ COMMITTED.  Si la opción READ\_COMMITTED\_SNAPSHOT se establece en OFF, deberá establecer explícitamente el nivel de aislamiento de instantáneas en cada sesión a fin de tener acceso a las filas con versión.  
  
## Administración de simultaneidad con niveles de aislamiento  
 El nivel de aislamiento con el que se ejecuta una instrucción Transact\-SQL determina su comportamiento de bloqueo y de versión de fila.  Un nivel de aislamiento afecta a todo el ámbito de la conexión y, una vez que se establece para una conexión con la instrucción SET TRANSACTION ISOLATION LEVEL, permanece activo hasta que se cierra la conexión o se establece otro nivel de aislamiento.  Cuando se cierra una conexión y se devuelve al grupo, se mantiene el nivel de aislamiento de la última instrucción SET TRANSACTION ISOLATION LEVEL.  Las conexiones posteriores que vuelvan a usar una conexión agrupada emplearán el nivel de aislamiento en vigor en el momento de la agrupación de la conexión.  
  
 Las consultas individuales emitidas en una conexión pueden contener sugerencias de bloqueo que modifiquen el aislamiento de una única instrucción o transacción, pero que no afecten al nivel de aislamiento de la conexión.  Los niveles de aislamiento o sugerencias de bloqueo establecidos en los procedimientos almacenados o en las funciones no cambian el nivel de aislamiento de la conexión que los llama y solo están activos lo que dura la llamada al procedimiento almacenado o a la función.  
  
 En las versiones anteriores de SQL Server se admitían cuatro niveles de aislamiento definidos en el estándar SQL\-92:  
  
-   READ UNCOMMITTED es el nivel de aislamiento menos restrictivo porque omite los bloqueos realizados por otras transacciones.  Las transacciones que se ejecutan con READ UNCOMMITTED pueden leer valores de datos modificados que aún no han confirmado otras transacciones; éstos se conocen como lecturas no confirmadas.  
  
-   READ COMMITTED es el nivel de aislamiento predeterminado en SQL Server.  Impide las lecturas no confirmadas al especificar que las instrucciones no pueden leer valores de datos modificados que aún no hayan confirmado otras transacciones.  Otras transacciones podrán modificar, insertar o eliminar datos entre ejecuciones de instrucciones individuales en la transacción actual, lo que dará lugar a lecturas irrepetibles o datos "fantasma".  
  
-   REPEATABLE READ es un nivel de aislamiento más restrictivo que READ COMMITTED.  Incluye READ COMMITTED y además especifica que ninguna otra transacción puede modificar ni eliminar datos que la transacción actual haya leído hasta que ésta no se confirme.  La simultaneidad es menor que en READ COMMITTED porque durante la transacción se mantienen bloqueos compartidos en los datos leídos en lugar de liberarlos al final de cada instrucción.  
  
-   SERIALIZABLE es el nivel de aislamiento más restrictivo, dado que bloquea intervalos enteros de claves y mantiene los bloqueos hasta que se completa la transacción.  Incluye REPEATABLE READ y agrega la restricción de que otras transacciones no pueden insertar filas nuevas en intervalos que haya leído la transacción hasta que ésta no se complete.  
  
 Para obtener más información, vea "Niveles de aislamiento" en los Libros en pantalla de SQL Server.  
  
### Extensiones del nivel de aislamiento de instantáneas  
 SQL Server 2005 presentaba extensiones a los niveles de aislamiento SQL\-92 con la introducción del nivel de aislamiento SNAPSHOT y una implementación adicional de READ COMMITTED.  El nivel de aislamiento READ\_COMMITTED\_SNAPSHOT puede reemplazar de forma transparente a READ COMMITTED en todas las transacciones.  
  
-   El aislamiento SNAPSHOT especifica que los datos leídos en una transacción nunca reflejarán los cambios que otras transacciones simultáneas hayan realizado.  Cuando una transacción comienza, utiliza las versiones de filas de datos que existen.  No existen bloqueos en los datos cuando se leen, de modo que las transacciones SNAPSHOT no impiden que otras transacciones escriban datos.  Las transacciones que escriben datos no impiden que las transacciones de instantáneas los lean.  Para utilizar la opción de base de datos ALLOW\_SNAPSHOT\_ISOLATION, deberá habilitar el aislamiento de instantáneas.  
  
-   Cuando el aislamiento de instantáneas está habilitado en una base de datos, la opción de base de datos READ\_COMMITTED\_SNAPSHOT determina el comportamiento del nivel de aislamiento predeterminado READ COMMITTED.  Si no especifica explícitamente READ\_COMMITTED\_SNAPSHOT ON, READ COMMITTED se aplica a todas las transacciones implícitas.  Esto produce el mismo comportamiento que se si establece READ\_COMMITTED\_SNAPSHOT OFF \(el valor predeterminado\).  Cuando READ\_COMMITTED\_SNAPSHOT OFF está activo, el motor de base de datos utiliza bloqueos compartidos para exigir el nivel de aislamiento predeterminado.  Si establece la opción de base de datos READ\_COMMITTED\_SNAPSHOT en ON, el motor de base de datos utiliza la versión de fila y el aislamiento de instantáneas como valor predeterminado, en lugar de utilizar bloqueos para proteger los datos.  
  
## Cómo funcionan el aislamiento de instantáneas y la versión de fila  
 Cuando se habilita el nivel de aislamiento SNAPSHOT, cada vez que se actualiza una fila, el motor de base de datos de SQL Server almacena una copia de la fila original en **tempdb** y agrega un número de secuencia de transacción a la fila.  A continuación se muestra la secuencia de eventos que tienen lugar:  
  
-   Se inicia una nueva transacción y se le asigna un número de secuencia de transacción.  
  
-   El motor de base de datos lee una fila de la transacción y recupera la versión de fila de **tempdb** cuyo número de secuencia se aproxima más a, y es inferior a, el número de la secuencia de transacción.  
  
-   Luego, comprueba que el número de la secuencia de transacción no esté en la lista de números de secuencia de transacción de las transacciones no confirmadas activas cuando se inició la transacción de instantánea.  
  
-   La transacción lee la versión de la fila de **tempdb** que era la actual desde que se inició la transacción.  No verá las nuevas filas insertadas después, dado que esos valores de número de secuencia serán superiores al valor del número de la secuencia de transacción.  
  
-   La transacción actual verá las filas que se eliminaron después de su comienzo, porque habrá una versión de fila en **tempdb** con un valor de número de secuencia inferior.  
  
 El efecto global del aislamiento de instantáneas es que la transacción, a su comienzo, ve todos los datos que existen, sin tener en cuenta ni realizar ningún bloqueo en las tablas subyacentes.  Como resultado, puede haber mejoras en el rendimiento en aquellas situaciones en las que hay contención.  
  
 Una transacción de instantánea siempre utiliza un control de simultaneidad optimista, que retiene los bloqueos que impedirían que otras transacciones actualizaran filas.  Si una transacción de instantánea intenta confirmar una actualización en una fila que se cambió después de que comenzara, la transacción se revierte y se genera un error.  
  
## Trabajo con aislamiento de instantáneas en ADO.NET  
 El aislamiento de instantáneas se admite en ADO.NET mediante la clase <xref:System.Data.SqlClient.SqlTransaction>.  Si se ha habilitado en una base de datos el aislamiento de instantáneas pero no se ha configurado como READ\_COMMITTED\_SNAPSHOT ON, deberá iniciar una <xref:System.Data.SqlClient.SqlTransaction> mediante el valor de enumeración **IsolationLevel.Snapshot** cuando llame al método <xref:System.Data.SqlClient.SqlConnection.BeginTransaction%2A>.  Este fragmento de código asume que la conexión es un objeto <xref:System.Data.SqlClient.SqlConnection> abierto.  
  
```vb  
Dim sqlTran As SqlTransaction = _  
  connection.BeginTransaction(IsolationLevel.Snapshot)  
```  
  
```csharp  
SqlTransaction sqlTran =   
  connection.BeginTransaction(IsolationLevel.Snapshot);  
```  
  
### Ejemplo  
 El siguiente ejemplo demuestra cómo se comportan los diferentes niveles de aislamiento al intentar tener acceso a los datos bloqueados, y no está pensado para su uso en código de producción.  
  
 El código conecta a la base de datos de ejemplo **AdventureWorks** de SQL Server, crea una tabla llamada **TestSnapshot** e inserta una fila de datos.  El código utiliza la instrucción ALTER DATABASE de Transact\-SQL para activar el aislamiento de instantáneas en la base de datos, pero no establece la opción READ\_COMMITTED\_SNAPSHOT, lo que deja activo el comportamiento de nivel de aislamiento predeterminado READ COMMITTED.  Luego, el código realiza las siguientes acciones:  
  
-   Inicia, pero no completa, sqlTransaction1, que utiliza el nivel de aislamiento SERIALIZABLE para iniciar una transacción de actualización.  El resultado es que la tabla se bloquea.  
  
-   Se abre una segunda conexión y se inicia una segunda transacción con el nivel de aislamiento SNAPSHOT para leer los datos de la tabla **TestSnapshot**.  Como el aislamiento de instantáneas está habilitado, esta transacción puede leer los datos que existían antes de que se iniciara sqlTransaction1.  
  
-   Se abre una tercera conexión y se inicia una transacción con el nivel de aislamiento READ COMMITTED para intentar leer los datos de la tabla.  En este caso, el código no puede leer los datos porque no puede leer con posterioridad a los bloqueos realizados en la tabla en la primera transacción y el tiempo de espera se agota.  El mismo resultado se produciría si se utilizaran los niveles de aislamiento REPEATABLE READ y SERIALIZABLE, ya que estos niveles no pueden leer después de los bloqueos realizados en la primera transacción.  
  
-   Se abre una cuarta conexión y se inicia una transacción con el nivel de aislamiento READ UNCOMMITTED, que realiza una lectura no confirmada del valor sin confirmar de sqlTransaction1.  Puede que este valor no exista nunca realmente en la base de datos si la primera transacción no se confirma.  
  
-   Se revierte la primera transacción y se procede a una limpieza con la eliminación de la tabla **TestSnapshot** y la desactivación del aislamiento de instantáneas en la base de datos **AdventureWorks**.  
  
> [!NOTE]
>  En los siguientes ejemplos se usa la misma cadena de conexión con la agrupación de conexiones desactivada.  Si una conexión está agrupada, el restablecimiento de su nivel de aislamiento no restablece el nivel de aislamiento en el servidor.  Así, las conexiones posteriores que utilicen la misma conexión interna agrupada se iniciarán con los niveles de aislamiento establecidos en el nivel de la conexión agrupada.  Una alternativa a la desconexión de la agrupación de conexiones consiste en establecer el nivel de aislamiento de forma explícita para cada conexión.  
  
 [!code-csharp[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.Demo#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.Demo/VB/source.vb#1)]  
  
### Ejemplo  
 En el siguiente ejemplo se muestra el comportamiento del aislamiento de instantáneas cuando se están modificando los datos.  El código realiza las siguientes acciones:  
  
-   Conecta a la base de datos de ejemplo **AdventureWorks** y habilita el aislamiento SNAPSHOT.  
  
-   Crea una tabla llamada **TestSnapshotUpdate** e inserta tres filas de datos de ejemplo.  
  
-   Inicia, pero no completa, sqlTransaction1 mediante el aislamiento SNAPSHOT.  Se seleccionan tres filas de datos en la transacción.  
  
-   Crea una segunda **SqlConnection** a **AdventureWorks** y crea una segunda transacción con el nivel de aislamiento READ COMMITTED que actualiza un valor de una de las filas seleccionadas en sqlTransaction1.  
  
-   Confirma sqlTransaction2.  
  
-   Vuelve a sqlTransaction1 e intenta actualizar la misma fila que sqlTransaction1 ya ha confirmado.  Se produce el Error 3960 y sqlTransaction1 se revierte automáticamente.  El **SqlException.Number** y el **SqlException.Message** se muestran en la ventana Consola.  
  
-   Ejecuta el código de limpieza para desactivar el aislamiento de instantáneas en **AdventureWorks** y eliminar la tabla **TestSnapshotUpdate**.  
  
 [!code-csharp[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/CS/source.cs#1)]
 [!code-vb[DataWorks SnapshotIsolation.DemoUpdate#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SnapshotIsolation.DemoUpdate/VB/source.vb#1)]  
  
### Uso de sugerencias de bloqueo con aislamiento de instantáneas  
 En el ejemplo anterior, la primera transacción selecciona los datos y una segunda transacción los actualiza antes de que la primera pueda completarse, lo que crea un conflicto de actualización cuando ésta intenta actualizar la misma fila.  Para reducir la posibilidad de conflictos de actualización en transacciones de instantáneas cuya ejecución tiene una larga duración, suministre sugerencias de bloqueo al comienzo de la transacción.  La siguiente instrucción SELECT utiliza la sugerencia UPDLOCK para bloquear las filas seleccionadas:  
  
```  
SELECT * FROM TestSnapshotUpdate WITH (UPDLOCK)   
  WHERE PriKey BETWEEN 1 AND 3  
```  
  
 El uso de la sugerencia de bloqueo UPDLOCK bloquea las transacciones que intentan actualizar las filas antes de que se complete la primera transacción.  De esta manera se garantiza que las filas seleccionadas no tienen conflictos cuando posteriormente se actualizan en la transacción.  Consulte "Sugerencias de bloqueo" en los Libros en pantalla de SQL Server.  
  
 Si la aplicación tiene muchos conflictos, el aislamiento de instantáneas podría no ser la mejor elección.  Las sugerencias únicamente deben utilizarse cuando sea necesario.  La aplicación no debería estar diseñada para que dependa constantemente de las sugerencias de bloqueo para su funcionamiento.  
  
## Vea también  
 [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)