---
description: 'Más información sobre: Tutorial: manipular datos (C#)'
title: 'Tutorial: Manipular datos (C#)'
ms.date: 03/30/2017
ms.assetid: 24adfbe0-0ad6-449f-997d-8808e0770d2e
ms.openlocfilehash: 6176709a2e02d8c06ec54b70cc6e0e4c302509c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729593"
---
# <a name="walkthrough-manipulating-data-c"></a>Tutorial: Manipular datos (C#)

Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos. Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C#.  
  
## <a name="prerequisites"></a>Requisitos previos  

 En este tutorial se requiere lo siguiente:  
  
- Este tutorial utiliza una carpeta dedicada ("c:\linqtest6") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
- Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest6.  
  
- Un archivo de código de C# generado a partir de la base de datos Northwind.  
  
     Puede generar este archivo mediante el Object Relational Designer o la herramienta SQLMetal. Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:  
  
     **sqlmetal /code:"c:\linqtest6\northwind.cs" /language:csharp "C:\linqtest6\northwnd.mdf" /pluralize**  
  
     Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Información general  

 Este tutorial se compone de seis tareas principales:  
  
- Crear la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.  
  
- Agregar el archivo de código de la base de datos al proyecto.  
  
- Crear el nuevo objeto de cliente.  
  
- Modificar el nombre de contacto de un cliente.  
  
- Eliminar un pedido.  
  
- Enviar estos cambios a la base de datos Northwind.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Crear una solución LINQ to SQL  

 En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Para crear una solución LINQ to SQL  
  
1. En el menú **archivo** de Visual Studio, elija **nuevo** y, a continuación, haga clic en **proyecto**.  
  
2. En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual C#**.  
  
3. En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
4. En el cuadro **nombre** , escriba **LinqDataManipulationApp**.  
  
5. En el cuadro **Ubicación** , compruebe dónde desea almacenar los archivos del proyecto.  
  
6. Haga clic en **Aceptar**.  
  
## <a name="adding-linq-references-and-directives"></a>Agregar referencias y directivas LINQ  

 En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada. Si System.Data.Linq no se incluye como referencia en el proyecto, agréguelo, como se explica en los pasos siguientes:  
  
#### <a name="to-add-systemdatalinq"></a>Para agregar System.Data.Linq  
  
1. En **Explorador de soluciones**, haga clic con el botón secundario en **referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
2. En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
3. Agregue las directivas siguientes al principio de Program.cs:  
  
     [!code-csharp[DLinqWalk3CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Agregar el archivo de código de Northwind al proyecto  

 En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Para agregar el archivo de código de Northwind al proyecto  
  
1. En el menú **Proyecto** , haga clic en **Agregar elemento existente**.  
  
2. En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest6\northwind.CS y, a continuación, haga clic en **Agregar**.  
  
     El archivo northwind.cs se agrega al proyecto.  
  
## <a name="setting-up-the-database-connection"></a>Configurar la conexión a la base de datos  

 Primero, pruebe su conexión a la base de datos. Observe en particular que la base de datos, Northwnd, no tiene la i. Si se generan errores en los pasos siguientes, revise el archivo northwind.cs para determinar cómo se escribe el nombre de la clase parcial de Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>Para configurar y probar la conexión a la base de datos  
  
1. Escriba o pegue el código siguiente en el método `Main`, en la clase Program:  
  
     [!code-csharp[DLinqWalk3CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#2)]  
  
2. Presione F5 para probar la aplicación en este punto.  
  
     Se abre una ventana de **consola** .  
  
     Para cerrar la aplicación, presione Entrar en la ventana de la **consola** o haga clic en **detener depuración** en el menú **depurar** de Visual Studio.  
  
## <a name="creating-a-new-entity"></a>Crear una nueva entidad  

 Crear entidades es sencillo. Puede crear objetos (como `Customer`) mediante la palabra clave `new`.  
  
 En esta sección y las siguientes, realizará cambios solo en la memoria caché local. No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>Para agregar un nuevo objeto entidad Customer  
  
1. Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine();` en el método `Main`:  
  
     [!code-csharp[DLinqWalk3CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#3)]  
  
2. Presione F5 para depurar la solución.  
  
3. Presione entrar en la ventana de la **consola** para detener la depuración y continuar con el tutorial.  
  
## <a name="updating-an-entity"></a>Actualización de una entidad  

 En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Para cambiar el nombre de un cliente  
  
- Agregue el código siguiente encima de `Console.ReadLine();`:  
  
     [!code-csharp[DLinqWalk3CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#4)]  
  
## <a name="deleting-an-entity"></a>Eliminación de una entidad  

 Con el mismo objeto de cliente, puede eliminar el primer pedido.  
  
 El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos. Agregue el código siguiente delante de `Console.ReadLine` para ver cómo se pueden eliminar los objetos:  
  
#### <a name="to-delete-a-row"></a>Para eliminar una fila  
  
- Agregue el código siguiente justo encima de `Console.ReadLine();`:  
  
     [!code-csharp[DLinqWalk3CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Enviar los cambios a la base de datos  

 El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos. Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.  
  
#### <a name="to-submit-changes-to-the-database"></a>Para enviar los cambios a la base de datos  
  
1. Inserte el código siguiente justo encima de `Console.ReadLine`:  
  
     [!code-csharp[DLinqWalk3CS#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#6)]  
  
2. Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:  
  
     [!code-csharp[DLinqWalk3CS#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk3CS/cs/Program.cs#7)]  
  
3. Presione F5 para depurar la solución.  
  
4. Presione entrar en la ventana de la **consola** para cerrar la aplicación.  
  
> [!NOTE]
> Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está. Para ejecutar de nuevo la solución, cambie el nombre del cliente y el identificador de cliente que se debe agregar.  
  
## <a name="see-also"></a>Vea también

- [Aprender con tutoriales](learning-by-walkthroughs.md)
