---
title: "Tutorial: Modelo de objetos simple y consultas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Tutorial: Modelo de objetos simple y consultas (Visual Basic)
Este tutorial proporciona un escenario completo de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] básico, con las mínimas dificultades.  Creará una clase de entidad que modela la tabla Customers de la base de datos de ejemplo Northwind.  Después creará una consulta simple para enumerar los clientes que se encuentran en Londres.  
  
 Este tutorial está orientado a código por diseño, para que sea más sencillo mostrar los conceptos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Normalmente, para crear un modelo de objetos utilizaría el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual Basic.  
  
## Requisitos previos  
  
-   Este tutorial utiliza una carpeta dedicada \("c:\\linqtest"\) que contiene los archivos.  Cree esta carpeta antes de empezar el tutorial.  
  
-   Este tutorial requiere la base de datos de ejemplo Northwind.  Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.  Para obtener más información, consulte [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  Después de haber descargado la base de datos, copie el archivo en la carpeta c:\\linqtest.  
  
## Información general  
 Este tutorial se compone de seis tareas principales:  
  
-   Crear una solución [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
-   Asignar una clase a una tabla de base de datos.  
  
-   Designar propiedades en la clase para representar las columnas de base de datos.  
  
-   Especificar la conexión a la base de datos Northwind.  
  
-   Crear una consulta simple para ejecutarla en la base de datos.  
  
-   Ejecutar la consulta y observar los resultados.  
  
## Crear una solución LINQ to SQL  
 En esta primera tarea, va a crear una solución de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] que contiene las referencias necesarias para compilar y ejecutar un proyecto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
#### Para crear una solución LINQ to SQL  
  
1.  En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
2.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, haga clic en **Visual Basic**.  
  
3.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
4.  En el cuadro **Nombre**, escriba LinqConsoleApp.  
  
5.  Haga clic en **Aceptar**.  
  
## Agregar referencias y directivas LINQ  
 En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada.  Si `System.Data.Linq` no se incluye como referencia en su proyecto \(haga clic en **Mostrar todos los archivos** en el **Explorador de soluciones** y expanda el nodo **Referencias**\), agréguelo, como se explica en los pasos siguientes.  
  
#### Para agregar System.Data.Linq  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo **Agregar referencia**, haga clic en **.NET**, en el ensamblado System.Data.Linq y, a continuación, en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
3.  También en el cuadro de diálogo **Agregar referencia**, haga clic en **.NET**, desplácese hasta System.Windows.Forms y haga clic en él, y, a continuación, haga clic en **Aceptar**.  
  
     Este ensamblado, que permite usar el cuadro de mensaje en el tutorial, se agrega al proyecto.  
  
4.  Agregue las directivas siguientes antes de `Module1`:  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## Asignar una clase a una tabla de base de datos  
 En este paso, creará una clase y la asignará a una tabla de base de datos.  Este tipo de clase se denomina *clase de entidad*.  Observe que la asignación se realiza con solo agregar el atributo <xref:System.Data.Linq.Mapping.TableAttribute>.  La propiedad <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> especifica el nombre de la tabla de la base de datos.  
  
#### Para crear una clase de entidad y asignarla a una tabla de base de datos  
  
-   Escriba o pegue el código siguiente en Module1.vb, justo encima de `Sub Main`:  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## Designar propiedades en la clase para representar columnas de base de datos  
 En este paso, realizará varias tareas.  
  
-   Utilizará el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> para designar las propiedades `CustomerID` y `City` en la clase de entidad como representativas de las columnas de la tabla de base de datos.  
  
-   Designará la propiedad `CustomerID` como representativa de una columna de clave principal en la base de datos.  
  
-   Designará los campos `_CustomerID` y `_City` para el almacenamiento privado.  Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] podrá almacenar y recuperar los valores directamente, en lugar de utilizar descriptores de acceso públicos que podrían incluir lógica empresarial.  
  
#### Para representar las características de dos columnas de base de datos  
  
-   Escriba o pegue el código siguiente en Module1.vb, justo delante de `End Class`:  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## Especificar la conexión a la base de datos Northwind  
 En este paso, utilizará un objeto <xref:System.Data.Linq.DataContext> para establecer una conexión entre sus estructuras de datos basadas en código y la propia base de datos.  <xref:System.Data.Linq.DataContext> es el canal principal a través del cual se recuperan los objetos de la base de datos y se envían los cambios.  
  
 También declarará `Table(Of Customer)` para que actúe como la tabla lógica con tipo para las consultas que realizará en la tabla Customers de la base de datos.  Creará y ejecutar estas consultas en pasos posteriores.  
  
#### Para especificar la conexión a la base de datos  
  
-   Escriba o pegue el código siguiente en el método `Sub Main`.  
  
     Tenga en cuenta que se asume que el archivo `northwnd.mdf` está en la carpeta linqtest.  Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## Crear una consulta simple  
 En este paso, creará una consulta para buscar los clientes de la tabla de base de datos Customers que se encuentran en Londres.  En este paso, el código de la consulta simplemente la describe.  No la ejecuta.  Este enfoque se denomina *ejecución diferida*.  Para obtener más información, consulte [Introduction to LINQ Queries \(C\#\)](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md).  
  
 También generará un resultado de registro para mostrar los comandos SQL que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera.  Esta característica de registro \(que utiliza <xref:System.Data.Linq.DataContext.Log%2A>\) es útil para la depuración, así como para determinar que los comandos que se envían a la base de datos representan la consulta de manera precisa.  
  
#### Para crear una consulta simple  
  
-   Escriba o pegue el código siguiente en el método `Sub Main` después de la declaración `Table(Of Customer)`:  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## Ejecutar la consulta  
 En este paso es donde realmente ejecutará la consulta.  Las expresiones de consulta creadas en pasos anteriores no se evalúan hasta que no se necesitan los resultados.  Al comenzar la iteración `For Each`, se ejecuta un comando SQL en la base de datos y se materializan los objetos.  
  
#### Para ejecutar la consulta  
  
1.  Escriba o pegue el código siguiente al final del método `Sub Main` \(después de la descripción de la consulta\):  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2.  Presione F5 para depurar la aplicación.  
  
    > [!NOTE]
    >  Si la aplicación genera un error en tiempo de ejecución, consulte la sección Solución de problemas de [Aprender mediante tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)￼.  
  
     El cuadro de mensaje muestra una lista de seis clientes.  La ventana Consola muestra el código SQL generado.  
  
3.  Haga clic en **Aceptar** para descartar el cuadro de mensaje.  
  
     La aplicación se cierra.  
  
4.  En el menú **Archivo**, haga clic en **Guardar todo**.  
  
     Necesitará esta aplicación si va a continuar con el tutorial siguiente.  
  
## Pasos siguientes  
 El tema [Tutorial: Realizar consultas en varias relaciones \(Visual Basic\)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) continúa donde finaliza este tutorial.  El tutorial Realizar consultas en varias relaciones muestra cómo [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede realizar consultas entre tablas, de forma similar a las *combinaciones* en las bases de datos relacionales.  
  
 Si desea seguir los pasos del tutorial Realizar consultas en varias relaciones, no olvide guardar la solución del tutorial que acaba de completar, que es un requisito previo.  
  
## Vea también  
 [Aprender mediante tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)