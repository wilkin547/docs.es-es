---
title: "Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, improving efficiency"
ms.assetid: 5beb4983-80c2-4f60-8c51-a07f9fd94cb3
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Using BatchBlock and BatchedJoinBlock to Improve Efficiency
La biblioteca de flujos de datos TPL proporciona las clases <xref:System.Threading.Tasks.Dataflow.BatchBlock%601?displayProperty=fullName> y <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602?displayProperty=fullName> para poder recibir y almacenar en búfer datos de uno o más orígenes y después propagar esos datos almacenados en búfer como una colección.  Este mecanismo por lotes es útil cuando se recopilan datos de uno o más orígenes y después se procesan varios elementos de datos como un lote.  Por ejemplo, piense en una aplicación que usa flujo de datos para insertar registros en una base de datos.  Esta operación puede ser más eficaz si varios elementos se insertan al mismo tiempo en lugar de insertar de uno en uno de forma secuencial.  En este documento se describe cómo utilizar la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> para mejorar la eficacia de las operaciones de inserción de la base de datos.  También se describe cómo utilizar la clase <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> para capturar los resultados y cualquier excepción que se produce cuando el programa lee de una base de datos.  
  
> [!TIP]
>  La biblioteca de flujos de datos TPL \(espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Para instalar el espacio de nombres <xref:System.Threading.Tasks.Dataflow>, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **Administrar paquetes NuGet** en el menú Proyecto, y busque en línea el paquete `Microsoft.Tpl.Dataflow`.  
  
## Requisitos previos  
  
1.  Lea la sección sobre bloques de combinación en el documento [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) antes de iniciar este tutorial.  
  
2.  Asegúrese de que tiene una copia de la base de datos Northwind, Northwind.sdf, disponible en el equipo.  Este archivo se encuentra normalmente en la carpeta %Archivos de programa%\\Microsoft SQL Server Compact Edition\\v3.5\\Ejemplos\\.  
  
    > [!IMPORTANT]
    >  En algunas versiones de Windows, no podrá conectarse a Northwind.sdf si [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] se está ejecutando en modo que no sea de administrador.  Para conectarse a Northwind.sdf, inicie [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] o un símbolo del sistema de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] en modo **Ejecutar como administrador**.  
  
 Este tutorial contiene las siguientes secciones:  
  
-   [Crear la aplicación de consola](#creating)  
  
-   [Definir la clase Employee](#employeeClass)  
  
-   [Definir las operaciones de la base de datos de empleados](#operations)  
  
-   [Agregar datos de empleados a la base de datos sin usar el almacenamiento en búfer](#nonBuffering)  
  
-   [Usar el almacenamiento en búfer para agregar datos de empleados en la base de datos](#buffering)  
  
-   [Usar una combinación almacenada en búfer para leer datos de empleados de la base de datos](#bufferedJoin)  
  
-   [Ejemplo completo](#complete)  
  
<a name="creating"></a>   
## Crear la aplicación de consola  
  
<a name="consoleApp"></a>   
1.  En [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], cree un proyecto **Aplicación de consola** de Visual C\# o Visual Basic.  En este documento, el proyecto se denomina `DataflowBatchDatabase`.  
  
2.  En el proyecto, agregue una referencia a System.Data.SqlServerCe.dll y una referencia a System.Threading.Tasks.Dataflow.dll.  
  
3.  Asegúrese de que Form1.cs \(Form1.vb para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) contiene las siguientes instrucciones `using` \(`Imports` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
     [!code-csharp[TPLDataflow_BatchDatabase#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#1)]
     [!code-vb[TPLDataflow_BatchDatabase#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#1)]  
  
4.  Agregue a la clase `Program` los miembros de datos siguientes:  
  
     [!code-csharp[TPLDataflow_BatchDatabase#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#2)]
     [!code-vb[TPLDataflow_BatchDatabase#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#2)]  
  
<a name="employeeClass"></a>   
## Definir la clase Employee  
 Agregue la clase `Program` a la clase `Employee`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#3)]
 [!code-vb[TPLDataflow_BatchDatabase#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#3)]  
  
 La clase `Employee` contiene tres propiedades `EmployeeID`, `LastName` y `FirstName`.  Estas propiedades corresponden a las columnas `Employee ID`, `Last Name` y `First Name` en la tabla `Employees` de la base de datos Northwind.  Para esta demostración, la clase `Employee` también define el método `Random`, que crea un objeto `Employee` con valores aleatorios para sus propiedades.  
  
<a name="operations"></a>   
## Definir las operaciones de la base de datos de empleados  
 Agregue a la clase `Program` los métodos `InsertEmployees`, `GetEmployeeCount` y `GetEmployeeID`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#4)]
 [!code-vb[TPLDataflow_BatchDatabase#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#4)]  
  
 El método `InsertEmployees` agrega nuevos registros de empleados en la base de datos.  El método `GetEmployeeCount` recupera el número de entradas de la tabla `Employees`.  El método `GetEmployeeID` recupera el identificador del primer empleado con el nombre proporcionado.  Cada uno de estos métodos lleva una cadena de conexión la base de datos Northwind y utiliza la funcionalidad del espacio de nombres `System.Data.SqlServerCe` para comunicarse con la base de datos.  
  
<a name="nonBuffering"></a>   
## Agregar datos de empleados a la base de datos sin usar el almacenamiento en búfer  
 Agregue a la clase `Program` los métodos `AddEmployees` y `PostRandomEmployees`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#5)]
 [!code-vb[TPLDataflow_BatchDatabase#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#5)]  
  
 El método `AddEmployees` agrega datos del empleado en la base de datos mediante el flujo de datos.  También crea un objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> que llama al método `InsertEmployees` para agregar una entrada de empleado en la base de datos.  A continuación, el método `AddEmployees` llama al método `PostRandomEmployees` para enviar varios objetos `Employee` al objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.  El método `AddEmployees` espera que todas las operaciones de inserción finalicen.  
  
<a name="buffering"></a>   
## Usar el almacenamiento en búfer para agregar datos de empleados en la base de datos  
 Agregue a la clase `Program` el método `AddEmployeesBatched`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#6)]
 [!code-vb[TPLDataflow_BatchDatabase#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#6)]  
  
 Este método es similar a `AddEmployees`, salvo que también utiliza la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> para almacenar en búfer varios objetos `Employee` antes de enviar esos objetos al objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>.  Dado que la clase <xref:System.Threading.Tasks.Dataflow.BatchBlock%601> propaga varios elementos como una colección, el objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> se modifica para actuar sobre una matriz de objetos `Employee`.  Como en el método `AddEmployees`, `AddEmployeesBatched` llama al método `PostRandomEmployees` para enviar varios objetos `Employee`; sin embargo, `AddEmployeesBatched` envía estos objetos al objeto <xref:System.Threading.Tasks.Dataflow.BatchBlock%601>.  El método `AddEmployeesBatched`  también espera que todas las operaciones de inserción finalicen.  
  
<a name="bufferedJoin"></a>   
## Usar una combinación almacenada en búfer para leer datos de empleados de la base de datos  
 Agregue a la clase `Program` el método `GetRandomEmployees`.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#7)]
 [!code-vb[TPLDataflow_BatchDatabase#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#7)]  
  
 Este método imprime información sobre empleados aleatorios en la consola.  Crea varios objetos `Employee` aleatorios y llama al método `GetEmployeeID` para recuperar el identificador único para cada objeto.  Debido a que el método `GetEmployeeID` produce una excepción si no hay ningún empleado coincidente con los nombres y apellidos dados, el método `GetRandomEmployees` utiliza la clase <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> para almacenar objetos `Employee` para llamadas correctas a `GetEmployeeID` y objetos <xref:System.Exception?displayProperty=fullName> para llamadas que dan error.  El objeto <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> en este ejemplo actúa sobre un objeto <xref:System.Tuple%602> que contiene una lista de objetos `Employee` y una lista de objetos <xref:System.Exception>.  El objeto <xref:System.Threading.Tasks.Dataflow.BatchedJoinBlock%602> propaga estos datos cuando la suma del objeto `Employee` y <xref:System.Exception> recibido es igual que el tamaño del lote.  
  
<a name="complete"></a>   
## Ejemplo completo  
 El ejemplo siguiente muestra el código completo:  El método `Main` compara el tiempo necesario para realizar inserciones por lotes de la base de datos frente al tiempo necesario para realizar inserciones sin lotes de la base de datos.  También muestra el uso de una combinación almacenada en búfer para leer datos de empleados de la base de datos, así como notificar errores.  
  
 [!code-csharp[TPLDataflow_BatchDatabase#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_batchdatabase/cs/dataflowbatchdatabase.cs#100)]
 [!code-vb[TPLDataflow_BatchDatabase#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_batchdatabase/vb/dataflowbatchdatabase.vb#100)]  
  
## Vea también  
 [Flujo de datos](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)