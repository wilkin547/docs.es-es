---
title: "Consideraciones de rendimiento (Entity Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 61913f3b-4f42-4d9b-810f-2a13c2388a4a
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Consideraciones de rendimiento (Entity Framework)
En este tema se describen las características de rendimiento de ADO.NET Entity Framework y se facilitan algunas consideraciones para ayudar a mejorar el rendimiento de las aplicaciones de Entity Framework.  
  
## Fases de la ejecución de consultas  
 Para entender mejor el rendimiento de las consultas en Entity Framework, resulta útil comprender las operaciones que se realizan cuando se ejecuta una consulta en un modelo conceptual y se devuelven datos como objetos.  En la tabla siguiente se describe esta serie de operaciones.  
  
|Operación|Costo relativo|Frecuencia|Comentarios|  
|---------------|--------------------|----------------|-----------------|  
|Cargar los metadatos|Moderado|Una vez en cada dominio de aplicación.|Los metadatos de la asignación y del modelo usados por Entity Framework se cargan en una instancia de <xref:System.Data.Metadata.Edm.MetadataWorkspace>.  Estos metadatos se almacenan globalmente en caché y están disponibles para otras instancias de <xref:System.Data.Objects.ObjectContext> en el mismo dominio de aplicación.|  
|Abrir la conexión de la base de datos|Moderado<sup>1</sup>|Según sea necesario.|Dado que una conexión abierta con la base de datos consume recursos valiosos, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] abre y cierra dicha conexión según sea necesario.  También puede abrir explícitamente la conexión.  Para obtener más información, consulta [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).|  
|Generar vistas|Alto|Una vez en cada dominio de aplicación.  \(Se pueden generar previamente\).|Antes de que Entity Framework pueda ejecutar una consulta en un modelo conceptual o guardar los cambios realizados en el origen de datos, debe generar un conjunto de vistas de consulta locales para obtener acceso a la base de datos.  Debido al alto costo de generar estas vistas, es posible generarlas previamente y agregarlas al proyecto en tiempo de diseño.  Para obtener más información, consulta [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/es-es/b18a9d16-e10b-4043-ba91-b632f85a2579).|  
|Preparar la consulta|Moderado<sup>2</sup>|Una vez para cada consulta única.|Incluye los costos para crear el comando de consulta, generar un árbol de comandos basado en los metadatos de asignación y del modelo, y definir la forma de los datos devueltos.  Dado que tanto los comandos de consulta de Entity SQL como las consultas LINQ se almacenan en memoria caché, las ejecuciones posteriores de la misma consulta tardarán menos tiempo.  Todavía puede usar consultas LINQ compiladas para reducir este costo en ejecuciones posteriores y las consultas compiladas pueden ser más eficaces que las consultas LINQ que se almacenan en memoria caché automáticamente.  Para obtener más información, consulta [Consultas compiladas \(LINQ to Entities\)](../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).  Para obtener información general acerca de la ejecución de consultas LINQ, vea [LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md). **Note:**  Las consultas LINQ to Entities que aplican el operador `Enumerable.Contains` a colecciones en memoria no se almacenan en memoria caché automáticamente.  Tampoco se permite parametrizar colecciones en memoria en consultas LINQ compiladas.|  
|Ejecutar la consulta|Bajo<sup>2</sup>|Una vez para cada consulta.|El costo de ejecutar el comando en el origen de datos usando el proveedor de datos de ADO.NET.  Dado que la mayoría de los orígenes de datos almacenan en la caché los planes de consulta, las posteriores ejecuciones de la misma consulta pueden tardar menos tiempo.|  
|Cargar y validar los tipos|Bajo<sup>3</sup>|Una vez para cada instancia de <xref:System.Data.Objects.ObjectContext>.|Los tipos se cargan y se validan con los tipos definidos por el modelo conceptual.|  
|Seguimiento|Bajo<sup>3</sup>|Una vez para cada objeto devuelto por una consulta.  <sup>4</sup>|Si una consulta usa la opción de combinación <xref:System.Data.Objects.MergeOption>, esta fase no afecta al rendimiento.<br /><br /> Si la consulta usa la opción de combinación <xref:System.Data.Objects.MergeOption>, <xref:System.Data.Objects.MergeOption> o <xref:System.Data.Objects.MergeOption>, el seguimiento de los resultados de la consulta se realiza en la instancia de <xref:System.Data.Objects.ObjectStateManager>.  Se genera una instancia de <xref:System.Data.EntityKey> para cada objeto devuelto por la consulta al que se ha hecho un seguimiento y se usa para crear un objeto <xref:System.Data.Objects.ObjectStateEntry> en la instancia de <xref:System.Data.Objects.ObjectStateManager>.  Si se encuentra un objeto <xref:System.Data.Objects.ObjectStateEntry> existente para la instancia de <xref:System.Data.EntityKey>, se devuelve dicho objeto.  Si se usa la opción <xref:System.Data.Objects.MergeOption> o <xref:System.Data.Objects.MergeOption>, el objeto se actualiza antes de ser devuelto.<br /><br /> Para obtener más información, consulta [Identity Resolution, State Management, and Change Tracking](http://msdn.microsoft.com/es-es/3bd49311-0e72-4ea4-8355-38fe57036ba0).|  
|Materializar los objetos|Moderado<sup>3</sup>|Una vez para cada objeto devuelto por una consulta.  <sup>4</sup>|El proceso de leer el objeto <xref:System.Data.Common.DbDataReader> devuelto, crear los objetos y establecer valores de propiedad basados en los valores de cada instancia de la clase <xref:System.Data.Common.DbDataRecord>.  Si el objeto ya existe en <xref:System.Data.Objects.ObjectContext> y la consulta usa las opciones de combinación <xref:System.Data.Objects.MergeOption> o <xref:System.Data.Objects.MergeOption>, esta fase no afecta al rendimiento.  Para obtener más información, consulta [Identity Resolution, State Management, and Change Tracking](http://msdn.microsoft.com/es-es/3bd49311-0e72-4ea4-8355-38fe57036ba0).|  
  
 <sup>1</sup> Cuando un proveedor de origen de datos implementa la agrupación de conexiones, el costo de abrir una conexión se distribuye entre todo el grupo.  El proveedor de datos .NET para SQL Server admite la agrupación de conexiones.  
  
 <sup>2</sup> El costo aumenta con la complejidad de la consulta.  
  
 <sup>3</sup> El costo total aumenta proporcionalmente al número de objetos devueltos por la consulta.  
  
 <sup>4</sup> Esta sobrecarga no es necesaria para las consultas de EntityClient, ya que estas devuelven una instancia de <xref:System.Data.EntityClient.EntityDataReader> en lugar de objetos.  Para obtener más información, consulta [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## Consideraciones adicionales  
 A continuación se muestran otras consideraciones que pueden afectar al rendimiento de las aplicaciones de Entity Framework.  
  
### Ejecución de la consulta  
 Dado que las consultas usan muchos recursos, considere detenidamente en qué punto del código y en qué equipo se va ejecutar una consulta.  
  
#### Ejecución diferida frente a ejecución inmediata  
 Cuando se crea una instancia de <xref:System.Data.Objects.ObjectQuery%601> o una consulta LINQ, la consulta no se puede ejecutar inmediatamente.  La ejecución de la consulta se aplaza hasta que se necesiten los resultados, como por ejemplo, durante una enumeración `foreach` \(C\#\) o `For Each` \(Visual Basic\) o cuando se asigna para rellenar una colección <xref:System.Collections.Generic.List%601>.  La ejecución de la consulta comienza inmediatamente cuando se llama al método <xref:System.Data.Objects.ObjectQuery%601.Execute%2A> de una <xref:System.Data.Objects.ObjectQuery%601> o cuando se llama a un método LINQ que devuelve una consulta singleton, como <xref:System.Linq.Enumerable.First%2A> o <xref:System.Linq.Enumerable.Any%2A>.  Para obtener más información, vea [Object Queries](http://msdn.microsoft.com/es-es/0768033c-876f-471d-85d5-264884349276) y [Ejecución de la consulta \(LINQ to Entities\)](../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).  
  
#### Ejecución de consultas LINQ en el cliente  
 Aunque la ejecución de una consulta LINQ se produce en el equipo que hospeda el origen de datos, algunas partes de dicha consulta se pueden evaluar en el equipo cliente.  Para obtener más información, vea la sección Ejecución en el almacén de [Ejecución de la consulta \(LINQ to Entities\)](../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).  
  
### Complejidad de la asignación y de la consulta  
 La complejidad de las consultas individuales y de la asignación en el modelo de entidades tendrá un efecto significativo en el rendimiento de las consultas.  
  
#### Complejidad de la asignación  
 Los modelos con una complejidad superior a la de una asignación unívoca simple entre entidades del modelo conceptual y tablas del modelo de almacenamiento generan comandos más complejos.  
  
#### Complejidad de la consulta  
 Las consultas que requieren un gran número de combinaciones en los comandos que se ejecutan en el origen de datos o que devuelven una gran cantidad de datos pueden afectar al rendimiento de las maneras siguientes:  
  
-   Las consultas realizadas en un modelo conceptual y que parecen sencillas pueden ocasionar la ejecución de consultas más complejas en el origen de datos.  Esto se puede producir porque Entity Framework traduce una consulta en un modelo conceptual en una consulta equivalente en el origen de datos.  Cuando un único conjunto de entidades en el modelo conceptual se asigna a varias tablas en el origen de datos, o cuando una relación entre entidades se asigna a una tabla de combinación, el comando de consulta ejecutado en la consulta del origen de datos puede requerir una o más combinaciones.  
  
    > [!NOTE]
    >  Use el método <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A> de las clases <xref:System.Data.EntityClient.EntityCommand> o <xref:System.Data.Objects.ObjectQuery%601> para ver los comandos que se ejecutan en el origen de datos para una consulta determinada.  Para obtener más información, consulta [How to: View the Store Commands](http://msdn.microsoft.com/es-es/f9771c6e-3b62-4b24-a5d4-55d68e14fa79).  
  
-   Las consultas de Entity SQL anidadas pueden crear combinaciones en el servidor y devolver un gran número de filas.  
  
     El siguiente es un ejemplo de una consulta anidada en una cláusula de proyección:  
  
    ```  
    SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2   
        FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1   
        FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
    ```  
  
     Además, provocan que la canalización de la consulta genere una consulta única con duplicación de objetos en las consultas anidadas.  Debido a esto, una sola columna se puede duplicar varias veces.  En algunas bases de datos, incluyendo SQL Server, esto puede ocasionar que la tabla TempDB crezca demasiado, lo que puede disminuir el rendimiento del servidor.  Conviene tener cuidado al ejecutar consultas anidadas.  
  
-   Las consultas que devuelven una gran cantidad de datos pueden disminuir el rendimiento si el cliente está realizando operaciones que tienen un consumo de recursos proporcional al tamaño del conjunto de resultados.  En casos como este, considere la posibilidad de limitar la cantidad de datos devuelta por la consulta.  Para obtener más información, consulta [How to: Page Through Query Results](http://msdn.microsoft.com/es-es/ffc0f920-e7de-42e0-9b12-ef356421d030).  
  
 Los comandos generados automáticamente por Entity Framework pueden ser más complejos que los comandos similares escritos explícitamente por un desarrollador de bases de datos.  Si necesita un control explícito sobre los comandos ejecutados en el origen de datos, considere la posibilidad de definir una asignación a una función con valores de tabla o a un procedimiento almacenado.  
  
#### Relaciones  
 Para obtener un rendimiento óptimo de las consultas, debe definir las relaciones entre entidades como asociaciones en el modelo de entidades y también como relaciones lógicas en el origen de datos.  
  
### Rutas de la consulta  
 De forma predeterminada, al ejecutar una consulta <xref:System.Data.Objects.ObjectQuery%601>, no se devuelven los objetos relacionados \(aunque los propios objetos que representan las relaciones lo son\).  Puede cargar objetos relacionados de una de las tres maneras siguientes:  
  
1.  Establezca la ruta de acceso de la consulta antes de que se ejecute <xref:System.Data.Objects.ObjectQuery%601>.  
  
2.  Llame al método `Load` sobre la propiedad de navegación expuesta por el objeto.  
  
3.  Establezca la opción <xref:System.Data.Objects.ObjectContextOptions.LazyLoadingEnabled%2A> del <xref:System.Data.Objects.ObjectContext> en `true`.  Observe que esto se realiza automáticamente al generar código del nivel de objeto con el [Entity Data Model Designer](http://msdn.microsoft.com/es-es/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  Para obtener más información, vea [Generated Code Overview](http://msdn.microsoft.com/es-es/6a88ea38-6a90-4107-bc33-531b79ce5b6a).  
  
 Cuando considere qué opción se debe usar, sea consciente de que hay una correlación entre el número de solicitudes a la base de datos y la cantidad de datos devueltos en una sola consulta.  Para obtener más información, consulta [Loading Related Objects](http://msdn.microsoft.com/es-es/452347d2-7b3b-44cd-9001-231299a28cb1).  
  
#### Usar las rutas de la consulta  
 Las rutas de la consulta definen el gráfico de los objetos devueltos por una consulta.  Al definir la ruta de una consulta, solo se requiere una solicitud única en la base de datos para que se devuelvan todos los objetos definidos por la ruta.  El uso de rutas de consulta puede dar lugar a la ejecución de comandos complejos en el origen de datos partiendo de consultas de objeto aparentemente simples.  Esto se produce porque se requieren una o más combinaciones para la devolución de objetos relacionados en una consulta única.  Esta complejidad es mayor en consultas con un modelo de entidades complejo, como una entidad con herencia o una ruta que incluye relaciones varios a varios.  
  
> [!NOTE]
>  Use el método <xref:System.Data.Objects.ObjectQuery.ToTraceString%2A> para ver el comando que se generará mediante una consulta <xref:System.Data.Objects.ObjectQuery%601>.  Para obtener más información, consulta [How to: View the Store Commands](http://msdn.microsoft.com/es-es/f9771c6e-3b62-4b24-a5d4-55d68e14fa79).  
  
 Cuando la ruta de una consulta incluye demasiados objetos relacionados o cuando los objetos contienen demasiados datos de fila, es posible que el origen de datos no pueda completar la consulta.  Esto sucede si la consulta requiere un almacenamiento temporal intermedio que supera la capacidad del origen de datos.  Cuando esto se produce, se puede reducir la complejidad de la consulta del origen de datos cargando explícitamente los objetos relacionados.  
  
#### Cargar explícitamente los objetos relacionados  
 Puede cargar explícitamente los objetos relacionados llamando al método `Load` de una propiedad de navegación que devuelve una <xref:System.Data.Objects.DataClasses.EntityCollection%601> o <xref:System.Data.Objects.DataClasses.EntityReference%601>.  La carga explícita de objetos requiere un viaje de ida y vuelta a la base de datos cada vez que se llama al método `Load`.  
  
> [!NOTE]
>  Si llama al método `Load` mientras se recorre en bucle una colección de objetos devueltos, como cuando se usa la instrucción `foreach` \(`For Each` en Visual Basic\), el proveedor específico del origen de datos debe admitir varios conjuntos de resultados activos en una sola conexión.  En una base de datos de SQL Server, debe especificar un valor `MultipleActiveResultSets = true` en la cadena de conexión del proveedor.  
  
 También puede utilizar el método <xref:System.Data.Objects.ObjectContext.LoadProperty%2A> cuando no haya propiedades <xref:System.Data.Objects.DataClasses.EntityReference%601> o <xref:System.Data.Objects.DataClasses.EntityCollection%601> en entidades.  Esto es útil cuando se usan entidades POCO.  
  
 Aunque la carga explícita de objetos relacionados reducirá el número de combinaciones y la cantidad de datos redundantes, `Load` requiere varias conexiones a la base de datos, lo que puede resultar costoso cuando se carga explícitamente un gran número de objetos.  
  
### Guardar los cambios  
 Cuando se llama al método <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> de una instancia de <xref:System.Data.Objects.ObjectContext>, se genera un comando de creación, actualización o eliminación independiente para cada objeto agregado, actualizado o eliminado en el contexto.  Estos comandos se ejecutan en el origen de datos en una transacción única.  Al igual que ocurre en las consultas, el rendimiento de las operaciones de creación, actualización y eliminación depende de la complejidad de la asignación en el modelo conceptual.  
  
### Transacciones distribuidas  
 Las operaciones de una transacción explícita que requieren recursos administrados por el coordinador de transacciones distribuidas \(DTC\) serán mucho más caras que las operaciones similares que no requieren DTC.  La promoción a DTC se producirá en las situaciones siguientes:  
  
-   Una transacción explícita con una operación en una base de datos de SQL Server 2000 u otro origen de datos que siempre promueve transacciones explícitas a DTC.  
  
-   Una transacción explícita con una operación en SQL Server 2005 cuando [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] administra la conexión.  Esto sucede porque SQL Server 2005 promueve a DTC cada vez que se cierra y se vuelve a abrir una conexión dentro de una transacción única, que es el comportamiento predeterminado de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Esta promoción de DTC no se realiza cuando se usa SQL Server 2008. Para evitar esta promoción al usar SQL Server 2005, debe abrir y cerrar la conexión explícitamente dentro de la transacción.  Para obtener más información, consulta [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).  
  
 Las transacciones explícitas se usan cuando se ejecutan una o varias operaciones dentro de una transacción <xref:System.Transactions>.  Para obtener más información, consulta [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).  
  
## Estrategias para mejorar el rendimiento  
 Para mejorar el rendimiento global de las consultas en Entity Framework, use las estrategias siguientes.  
  
#### Generar previamente las vistas  
 La generación de vistas basadas en un modelo de entidades supone un costo significativo la primera vez que una aplicación ejecuta una consulta.  Emplee la utilidad EdmGen.exe para generar previamente las vistas en forma de archivo de código de Visual Basic o de C\# que se puede agregar al proyecto durante el diseño.  También podría utilizar el Kit de herramientas de transformación de plantillas de texto para generar vistas precompiladas.  Las vistas generadas previamente se validan en tiempo de ejecución para garantizar su coherencia con la versión actual del modelo de entidades especificado.  Para obtener más información, vea [How to: Pre\-Generate Views to Improve Query Performance](http://msdn.microsoft.com/es-es/b18a9d16-e10b-4043-ba91-b632f85a2579) y el blog [Isolating Performance with Precompiled\/Pre\-generated Views in the Entity Framework 4](http://go.microsoft.com/fwlink/?LinkID=201337&clcid=0x409).  
  
 Al trabajar con modelos muy grandes, se aplica la siguiente consideración:  
  
 El formato de metadatos de .NET limita a 16,777.215 \(0xFFFFFF\) el número de caracteres de cadena de usuario en un binario dado.  Si está generando vistas para un modelo muy grande y el archivo de vista alcanza este límite de tamaño, recibirá el error de compilación "No queda espacio lógico para crear más cadenas de usuario".  Esta limitación de tamaño se aplica a todos los binarios administrados.  Para obtener más información, vea el [blog](http://go.microsoft.com/fwlink/?LinkId=201476), donde se explica cómo evitar el error al trabajar con modelos grandes y complejos.  
  
#### Considerar la posibilidad de usar la opción de combinación NoTracking en las consultas  
 El seguimiento de los objetos devueltos en el contexto del objeto tiene un costo implícito.  Para detectar cambios en los objetos y garantizar que varias solicitudes para la misma entidad lógica devuelvan la misma instancia del objeto, es necesario que los objetos se adjunten a una instancia de <xref:System.Data.Objects.ObjectContext>.  Si no tiene previsto realizar actualizaciones o eliminaciones en los objetos y no necesita la administración de identidades, considere la posibilidad de usar las opciones de combinación <xref:System.Data.Objects.MergeOption> al ejecutar las consultas.  
  
#### Devolver la cantidad correcta de datos  
 En algunos escenarios, la especificación de una ruta de consulta mediante el método <xref:System.Data.Objects.ObjectQuery%601.Include%2A> es mucho más rápida porque requiere menos recorridos de ida y vuelta a la base de datos.  Sin embargo, en otros escenarios, los recorridos adicionales de ida y vuelta a la base de datos para cargar los objetos relacionados pueden ser más rápidos porque las consultas más sencillas con menos combinaciones producen una menor cantidad de datos redundantes.  Por ello, se recomienda probar el rendimiento de varias maneras para recuperar los objetos relacionados.  Para obtener más información, consulta [Loading Related Objects](http://msdn.microsoft.com/es-es/452347d2-7b3b-44cd-9001-231299a28cb1).  
  
 Para evitar devolver demasiados datos en una sola consulta, considere la posibilidad de paginar los resultados de la consulta en grupos que sean más fáciles de administrar.  Para obtener más información, consulta [How to: Page Through Query Results](http://msdn.microsoft.com/es-es/ffc0f920-e7de-42e0-9b12-ef356421d030).  
  
#### Limitar el ámbito de ObjectContext  
 En la mayoría de los casos, deberá crear una instancia de <xref:System.Data.Objects.ObjectContext> dentro de una instrucción `using` \(`Using…End Using` en Visual Basic\).  Esto puede aumentar el rendimiento garantizando que los recursos asociados al contexto del objeto se eliminan automáticamente cuando el código sale del bloque de instrucciones.  Sin embargo, cuando los controles se enlazan a objetos administrados por el contexto del objeto, se debe mantener la instancia de <xref:System.Data.Objects.ObjectContext> mientras se necesite el enlace, y eliminarla posteriormente de forma manual.  Para obtener más información, consulta [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).  
  
#### Considerar la posibilidad de abrir manualmente la conexión de la base de datos  
 Cuando la aplicación ejecuta una serie de consultas de objeto o llama con frecuencia al método <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> para conservar las operaciones de creación, actualización y eliminación en el origen de datos, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] debe abrir y cerrar continuamente la conexión al origen de datos.  En estos casos, considere la posibilidad de abrir manualmente la conexión al comienzo de estas operaciones y cerrarla o eliminarla una vez finalizadas dichas operaciones.  Para obtener más información, consulta [Managing Connections and Transactions](http://msdn.microsoft.com/es-es/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).  
  
## Datos de rendimiento  
 Algunos datos de rendimiento para Entity Framework se publican en las entradas siguientes del [blog del equipo de ADO.NET](http://go.microsoft.com/fwlink/?LinkId=91905):  
  
-   [Explorar el rendimiento de ADO.NET Entity Framework \- Parte 1](http://go.microsoft.com/fwlink/?LinkId=123907)  
  
-   [Explorar el rendimiento de ADO.NET Entity Framework \- Parte 2](http://go.microsoft.com/fwlink/?LinkId=123909)  
  
-   [Comparación del rendimiento de ADO.NET Entity Framework](http://go.microsoft.com/fwlink/?LinkID=123913)  
  
## Vea también  
 [Consideraciones de desarrollo e implementación](../../../../../docs/framework/data/adonet/ef/development-and-deployment-considerations.md)