---
title: 'Tutorial: Modelo de objetos simple y consultas (C#)'
ms.date: 03/30/2017
ms.assetid: 419961cc-92d6-45f5-ae8a-d485bdde3a37
ms.openlocfilehash: 2c2529c828c0b02ec2f53c7ea899bbe728ba88d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-simple-object-model-and-query-c"></a>Tutorial: Modelo de objetos simple y consultas (C#)
Este tutorial proporciona un escenario completo de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] básico, con las mínimas dificultades. Creará una clase de entidad que modela la tabla Customers de la base de datos de ejemplo Northwind. Después creará una consulta simple para enumerar los clientes que se encuentran en Londres.  
  
 Este tutorial está orientado a código por diseño, para que sea más sencillo mostrar los conceptos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Normalmente, para crear un modelo de objetos utilizaría el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C#.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Este tutorial utiliza una carpeta dedicada ("c:\linqtest5") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
-   Este tutorial requiere la base de datos de ejemplo Northwind. Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo en la carpeta c:\linqtest5.  
  
## <a name="overview"></a>Información general  
 Este tutorial se compone de seis tareas principales:  
  
-   Crear un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.  
  
-   Asignar una clase a una tabla de base de datos.  
  
-   Designar propiedades en la clase para representar las columnas de base de datos.  
  
-   Especificar la conexión a la base de datos Northwind.  
  
-   Crear una consulta simple para ejecutarla en la base de datos.  
  
-   Ejecutar la consulta y observar los resultados.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Crear una solución LINQ to SQL  
 En esta primera tarea, se creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Para crear una solución LINQ to SQL  
  
1.  En Visual Studio **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **tipos de proyecto** panel de la **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#**.  
  
3.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
4.  En el **nombre** , escriba **LinqConsoleApp**.  
  
5.  En el **ubicación** cuadro, compruebe dónde desea almacenar los archivos de proyecto.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="adding-linq-references-and-directives"></a>Agregar referencias y directivas LINQ  
 En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada. Si System.Data.Linq no se incluye como referencia en el proyecto (expanda el **referencias** nodo **el Explorador de soluciones**), agréguelo, como se explica en los pasos siguientes.  
  
#### <a name="to-add-systemdatalinq"></a>Para agregar System.Data.Linq  
  
1.  En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
3.  Agregue las directivas siguientes al principio de **Program.cs**:  
  
     [!code-csharp[DLinqWalk1CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a>Asignar una clase a una tabla de base de datos  
 En este paso, creará una clase y la asignará a una tabla de base de datos. Esta clase se denomina un *clase de entidad*. Observe que la asignación se realiza con solo agregar el atributo <xref:System.Data.Linq.Mapping.TableAttribute>. La propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> especifica el nombre de la tabla de la base de datos.  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a>Para crear una clase de entidad y asignarla a una tabla de base de datos  
  
-   Escriba o pegue el código siguiente en Program.cs, justo encima de la declaración de la clase `Program`:  
  
     [!code-csharp[DLinqWalk1CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a>Designar propiedades en la clase para representar columnas de base de datos  
 En este paso, realizará varias tareas.  
  
-   Utilizará el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar las propiedades `CustomerID` y `City` en la clase de entidad como representativas de las columnas de la tabla de base de datos.  
  
-   Designará la propiedad `CustomerID` como representativa de una columna de clave principal en la base de datos.  
  
-   Designará los campos `_CustomerID` y `_City` para el almacenamiento privado. Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podrá almacenar y recuperar los valores directamente, en lugar de utilizar descriptores de acceso públicos que podrían incluir lógica empresarial.  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a>Para representar las características de dos columnas de base de datos  
  
-   Escriba o pegue el código siguiente en Program.cs, dentro de las llaves de la clase `Customer`.  
  
     [!code-csharp[DLinqWalk1CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a>Especificar la conexión a la base de datos Northwind  
 En este paso, utilizará un objeto <xref:System.Data.Linq.DataContext> para establecer una conexión entre sus estructuras de datos basadas en código y la propia base de datos. <xref:System.Data.Linq.DataContext> es el canal principal a través del cual se recuperan los objetos de la base de datos y se envían los cambios.  
  
 También declarará `Table<Customer>` para que actúe como la tabla lógica con tipo para las consultas que realizará en la tabla Customers de la base de datos. Creará y ejecutar estas consultas en pasos posteriores.  
  
#### <a name="to-specify-the-database-connection"></a>Para especificar la conexión a la base de datos  
  
-   Escriba o pegue el código siguiente en el método `Main`.  
  
     Tenga en cuenta que se asume que el archivo `northwnd.mdf` está en la carpeta linqtest5. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
     [!code-csharp[DLinqWalk1CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1CS/cs/Program.cs#4)]  
  
## <a name="creating-a-simple-query"></a>Crear una consulta simple  
 En este paso, creará una consulta para buscar los clientes de la tabla de base de datos Customers que se encuentran en Londres. En este paso, el código de la consulta simplemente la describe. No la ejecuta. Este enfoque se conoce como *ejecución diferida*. Para obtener más información, vea [Introduction to LINQ queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].  
  
 También generará un resultado de registro para mostrar los comandos SQL que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera. Esta característica de registro (que utiliza <xref:System.Data.Linq.DataContext.Log%2A>) es útil para la depuración, así como para determinar que los comandos que se envían a la base de datos representan la consulta de manera precisa.  
  
#### <a name="to-create-a-simple-query"></a>Para crear una consulta simple  
  
-   Escriba o pegue el código siguiente en el método `Main` después de la declaración `Table<Customer>`.  
  
     [!code-csharp[DLinqWalk1ACS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#5)]  
  
## <a name="executing-the-query"></a>Ejecutar la consulta  
 En este paso es donde realmente ejecutará la consulta. Las expresiones de consulta creadas en pasos anteriores no se evalúan hasta que no se necesitan los resultados. Al comenzar la iteración `foreach`, se ejecuta un comando SQL en la base de datos y se materializan los objetos.  
  
#### <a name="to-execute-the-query"></a>Para ejecutar la consulta  
  
1.  Escriba o pegue el código siguiente al final del método `Main` (después de la descripción de la consulta).  
  
     [!code-csharp[DLinqWalk1ACS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk1ACS/cs/Program.cs#6)]  
  
2.  Presione F5 para depurar la aplicación.  
  
    > [!NOTE]
    >  Si la aplicación genera un error en tiempo de ejecución, vea la sección de solución de problemas de [aprender con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
     Los resultados de la consulta en la ventana de la consola deberían ser similares a éstos:  
  
     `ID=AROUT, City=London`  
  
     `ID=BSBEV, City=London`  
  
     `ID=CONSH, City=London`  
  
     `ID=EASTC, City=London`  
  
     `ID=NORTS, City=London`  
  
     `ID=SEVES, City=London`  
  
3.  Presione Entrar en la ventana de la consola para cerrar la aplicación.  
  
## <a name="next-steps"></a>Pasos siguientes  
 El [Tutorial: realizar consultas en varias relaciones (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-csharp.md) tema continúa donde finaliza este tutorial. El tutorial de consultas en varias relaciones muestra cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede realizar consultas entre tablas, de forma similar a *combinaciones* en una base de datos relacional.  
  
 Si desea seguir los pasos del tutorial Realizar consultas en varias relaciones, no olvide guardar la solución del tutorial que acaba de completar, que es un requisito previo.  
  
## <a name="see-also"></a>Vea también  
 [Aprendizaje con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
