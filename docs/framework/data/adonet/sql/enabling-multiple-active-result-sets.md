---
title: "Habilitar conjuntos de resultados activos múltiples"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1d39d1666f63d7d6f7a6154a124280486c3fccce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="enabling-multiple-active-result-sets"></a>Habilitar conjuntos de resultados activos múltiples
MARS (Multiple Active Result Sets, conjuntos de resultados activos múltiples) es una característica que funciona con SQL Server y que permite la ejecución de varios lotes en una sola conexión. Cuando MARS está habilitado para su uso con SQL Server, cada objeto de comando usado agrega una sesión a la conexión.  
  
> [!NOTE]
>  Una única sesión MARS abre una conexión lógica para MARS y, a continuación, una conexión lógica para cada comando activo.  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a>Habilitación y deshabilitación de MARS en la cadena de conexión  
  
> [!NOTE]
>  Las siguientes cadenas de conexión usan el ejemplo **AdventureWorks** incluido con SQL Server de la base de datos. En las cadenas de conexión proporcionadas se supone que la base de datos está instalada en un servidor llamado MSSQL1. Modifique la cadena de conexión según sea necesario para su entorno.  
  
 La característica MARS está deshabilitada de forma predeterminada. Para habilitarla, agregue el par de palabra clave "MultipleActiveResultSets=True" a la cadena de conexión. "True" es el único valor válido para habilitar MARS. En el siguiente ejemplo se muestra cómo conectarse a una instancia de SQL Server y cómo especificar que se debe habilitar MARS.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 Para deshabilitarla, agregue el par de palabra clave "MultipleActiveResultSets=False" a la cadena de conexión. "False" es el único valor válido para deshabilitar MARS. En la siguiente cadena de conexión se muestra cómo deshabilitar MARS.  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a>Consideraciones especiales al utilizar MARS  
 En general, no es necesario modificar las aplicaciones existentes para utilizar una conexión habilitada para MARS. No obstante, si desea utilizar las características de MARS en las aplicaciones, debe comprender las siguientes consideraciones especiales.  
  
### <a name="statement-interleaving"></a>Entrelazado de instrucciones  
 Las operaciones MARS se ejecutan de forma sincrónica en el servidor. Se permite el entrelazado de las instrucciones SELECT y BULK INSERT. Sin embargo, las instrucciones de lenguaje de manipulación de datos (DML) y de lenguaje de definición de datos (DDL) se ejecutan atómicamente. Toda instrucción que intente ejecutarse mientras hay un lote atómico en ejecución quedará bloqueada. La ejecución paralela en el servidor no es una característica MARS.  
  
 Si se envían dos lotes en una conexión MARS, y uno de ellos contiene una instrucción SELECT y el otro una instrucción DML, la DML puede comenzar la ejecución dentro de la ejecución de la instrucción SELECT. Sin embargo, la instrucción DML debe ejecutarse hasta su finalización para que la instrucción SELECT pueda progresar. Si ambas instrucciones están en ejecución en la misma transacción, cualquier cambio realizado en una instrucción DML después de que se ha iniciado la ejecución de la instrucción SELECT no se verá en la operación de lectura.  
  
 Una instrucción WAITFOR dentro de una instrucción SELECT no produce la transacción mientras está en espera, es decir, hasta que no se produce la primera fila. Esto implica que mientras una instrucción WAITFOR está esperando, no se puede ejecutar ningún otro lote en la misma conexión.  
  
### <a name="mars-session-cache"></a>Caché de sesiones MARS  
 Cuando se abre una conexión y está habilitado MARS, se crea una sesión lógica que agrega sobrecarga adicional. Para minimizar la sobrecarga y mejorar el rendimiento, **SqlClient** almacena en caché la sesión MARS de una conexión. La caché contiene como máximo 10 sesiones MARS. El usuario no puede ajustar este valor. Si se alcanza el límite de sesiones, se crea una nueva sesión y no se genera un error. La caché y las sesiones contenidas en ella son por conexión; no se comparten entre conexiones. Cuando se libera una sesión, vuelve al grupo a menos que se haya alcanzado el límite superior del mismo. Si el grupo de caché está lleno, la sesión se cierra. Las sesiones MARS no expiran. Solo se limpian cuando se elimina el objeto de conexión. La caché de sesiones MARS no está precargada. Se carga cuando la aplicación necesita más sesiones.  
  
### <a name="thread-safety"></a>Seguridad para subprocesos  
 Las operaciones MARS no proporcionan seguridad para subprocesos.  
  
### <a name="connection-pooling"></a>Agrupación de conexiones  
 Las conexiones habilitadas para MARS se agrupan como cualquier otra conexión. Si una aplicación abre dos conexiones, una con MARS habilitado y la otra con MARS deshabilitado, las dos conexiones estarán en grupos distintos. Para obtener más información, consulte [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).  
  
### <a name="sql-server-batch-execution-environment"></a>Entorno de ejecución por lotes de SQL Server  
 Cuando se abre una conexión, se define un entorno predeterminado. A continuación, este entorno se copia en una sesión MARS lógica.  
  
 El entorno de ejecución por lotes incluye los siguientes componentes:  
  
-   Definición de opciones (por ejemplo, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)  
  
-   Contexto de seguridad (rol del usuario o de la aplicación)  
  
-   Contexto de la base de datos (base de datos actual)  
  
-   Las variables de estado de ejecución (por ejemplo, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)  
  
-   Tablas temporales de nivel superior  
  
 Con MARS, hay un entorno de ejecución predeterminado asociado con una conexión. Cada lote nuevo que comienza a ejecutarse en una conexión dada recibe una copia del entorno predeterminado. Cada vez que se ejecuta código en un lote dado, todos los cambios realizados en el entorno están en el ámbito del lote específico. Finalizada la ejecución, la configuración de ejecución se copia en el entorno predeterminado. En el caso de un único lote que emite varios comandos para que se ejecuten de forma secuencial en la misma transacción, la semántica es la misma a la expuesta por las conexiones que implican clientes o servidores anteriores.  
  
### <a name="parallel-execution"></a>Ejecución paralela  
 MARS no se ha diseñado para quitar todos los requisitos de varias conexiones en una aplicación. Si una aplicación necesita la ejecución paralela real de comandos en un servidor, se deben emplear varias conexiones.  
  
 Por ejemplo, vamos a analizar la siguiente situación. Se crean dos objetos de comando, uno para procesar un conjunto de resultados y el otro para actualizar los datos, que comparten una conexión común a través de MARS. En este escenario, el `Transaction`.`Commit` se produce un error en la actualización hasta que se han leído todos los resultados en el primer objeto de comando, lo que produce la excepción siguiente:  
  
 Mensaje: Contexto de transacción en uso por otra sesión.  
  
 Origen: proveedor de datos .NetSqlClient  
  
 Esperado: (NULL)  
  
 Recibido: System.Data.SqlClient.SqlException  
  
 Hay tres opciones para solucionar esta situación:  
  
1.  Iniciar la transacción una vez creado el lector y, así, no forma parte de la transacción. Cada actualización se convierte entonces en su propia transacción.  
  
2.  Confirmar todo el trabajo una vez cerrado el lector. Esto puede traer como consecuencia un lote considerable de actualizaciones.  
  
3.  No utilizar MARS, sino una conexión distinta para cada objeto de comando que tendría antes de MARS.  
  
### <a name="detecting-mars-support"></a>Detección de compatibilidad con MARS  
 Para comprobar la compatibilidad con MARS, una aplicación puede leer el valor `SqlConnection.ServerVersion`. El número principal debe ser 9 para SQL Server 2005 y 10 para SQL Server 2008.  
  
## <a name="see-also"></a>Vea también  
 [Conjuntos de resultados activos múltiples (MARS)](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
