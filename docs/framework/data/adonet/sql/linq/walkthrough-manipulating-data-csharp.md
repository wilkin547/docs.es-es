---
title: 'Tutorial: Manipular datos (C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: b9b19d4f9a1fb56ddabbf3584c1fb7bb29cd6d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357665"
---
# <a name="walkthrough-manipulating-data-c"></a>Tutorial: Manipular datos (C#)
Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos. Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C#.  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este tutorial se requiere lo siguiente:  
  
-   Este tutorial utiliza una carpeta dedicada ("c:\linqtest6") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
-   Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest6.  
  
-   Un archivo de código de C# generado a partir de la base de datos Northwind.  
  
     Puede generar este archivo mediante el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] o la herramienta SQLMetal. Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:  
  
     **SqlMetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" / plural**  
  
     Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Información general  
 Este tutorial se compone de seis tareas principales:  
  
-   Crear el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.  
  
-   Agregar el archivo de código de la base de datos al proyecto.  
  
-   Crear el nuevo objeto de cliente.  
  
-   Modificar el nombre de contacto de un cliente.  
  
-   Eliminar un pedido.  
  
-   Enviar estos cambios a la base de datos Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Crear una solución LINQ to SQL  
 En esta primera tarea, se creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Para crear una solución LINQ to SQL  
  
1.  En Visual Studio **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2.  En el **tipos de proyecto** panel en el **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#**.  
  
3.  En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
4.  En el **nombre** , escriba **LinqDataManipulationApp**.  
  
5.  En el **ubicación** cuadro, compruebe dónde desea almacenar los archivos de proyecto.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="adding-linq-references-and-directives"></a>Agregar referencias y directivas LINQ  
 En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada. Si System.Data.Linq no se incluye como referencia en el proyecto, agréguelo, como se explica en los pasos siguientes:  
  
#### <a name="to-add-systemdatalinq"></a>Para agregar System.Data.Linq  
  
1.  En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
3.  Agregue las directivas siguientes al principio de Program.cs:  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Agregar el archivo de código de Northwind al proyecto  
 En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Para agregar el archivo de código de Northwind al proyecto  
  
1.  En el **proyecto** menú, haga clic en **Agregar elemento existente**.  
  
2.  En el **Agregar elemento existente** cuadro de diálogo, vaya a c:\linqtest6\northwind.cs y, a continuación, haga clic en **agregar**.  
  
     El archivo northwind.cs se agrega al proyecto.  
  
## <a name="setting-up-the-database-connection"></a>Configurar la conexión a la base de datos  
 Primero, pruebe su conexión a la base de datos. Observe en particular que la base de datos, Northwnd, no tiene la i. Si se generan errores en los pasos siguientes, revise el archivo northwind.cs para determinar cómo se escribe el nombre de la clase parcial de Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>Para configurar y probar la conexión a la base de datos  
  
1.  Escriba o pegue el código siguiente en el método `Main`, en la clase Program:  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2.  Presione F5 para probar la aplicación en este punto.  
  
     A **consola** abre la ventana.  
  
     Puede cerrar la aplicación, presione ENTRAR en el **consola** ventana, o haga clic en **Detener depuración** en Visual Studio **depurar** menú.  
  
## <a name="creating-a-new-entity"></a>Crear una nueva entidad  
 Crear entidades es sencillo. Puede crear objetos (como `Customer`) mediante la palabra clave `new`.  
  
 En esta sección y las siguientes, realizará cambios solo en la memoria caché local. No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>Para agregar un nuevo objeto entidad Customer  
  
1.  Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine();` en el método `Main`:  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2.  Presione F5 para depurar la solución.  
  
3.  Presione ENTRAR en el **consola** ventana para detener la depuración y continuar con el tutorial.  
  
## <a name="updating-an-entity"></a>Actualizar una entidad  
 En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Para cambiar el nombre de un cliente  
  
-   Agregue el código siguiente encima de `Console.ReadLine();`:  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a>Eliminar una entidad  
 Con el mismo objeto de cliente, puede eliminar el primer pedido.  
  
 El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos. Agregue el código siguiente delante de `Console.ReadLine` para ver cómo se pueden eliminar los objetos:  
  
#### <a name="to-delete-a-row"></a>Para eliminar una fila  
  
-   Agregue el código siguiente justo encima de `Console.ReadLine();`:  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Enviar los cambios a la base de datos  
 El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos. Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.  
  
#### <a name="to-submit-changes-to-the-database"></a>Para enviar los cambios a la base de datos  
  
1.  Inserte el código siguiente justo encima de `Console.ReadLine`:  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2.  Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3.  Presione F5 para depurar la solución.  
  
4.  Presione ENTRAR en el **consola** ventana para cerrar la aplicación.  
  
> [!NOTE]
>  Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está. Para ejecutar de nuevo la solución, cambie el nombre del cliente y el identificador de cliente que se debe agregar.  
  
## <a name="see-also"></a>Vea también  
 [Aprendizaje con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
