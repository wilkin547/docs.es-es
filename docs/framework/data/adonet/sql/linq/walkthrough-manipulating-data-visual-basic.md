---
title: 'Tutorial: Manipular datos (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 1f6a54f6-ec33-452a-a37d-48122207bf14
ms.openlocfilehash: dbf18273e69ff0977f5d16ff179b8659865ef696
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164056"
---
# <a name="walkthrough-manipulating-data-visual-basic"></a>Tutorial: Manipular datos (Visual Basic)

Este tutorial proporciona un escenario completo fundamental de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para agregar, modificar y eliminar datos en una base de datos. Utilizará una copia de la base de datos de ejemplo Northwind para agregar un cliente, cambiar el nombre de un cliente y eliminar un pedido.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual Basic.  
  
## <a name="prerequisites"></a>Prerrequisitos  

 En este tutorial se requiere lo siguiente:  
  
- Este tutorial utiliza una carpeta dedicada ("c:\linqtest2") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
- Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest2.  
  
- Archivo de código de Visual Basic generado a partir de la base de datos Northwind.  
  
     Puede generar este archivo mediante el Object Relational Designer o la herramienta SQLMetal. Este tutorial se escribió utilizando la herramienta SQLMetal con la línea de comandos siguiente:  
  
     **sqlmetal /code:"c:\linqtest2\northwind.vb" /language:vb "C:\linqtest2\northwnd.mdf" /pluralize**  
  
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
  
1. En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.  
  
2. En el panel **tipos de proyecto** del cuadro de diálogo **nuevo proyecto** , haga clic en **Visual Basic**.  
  
3. En el panel **Plantillas**, haga clic en **Aplicación de consola**.  
  
4. En el cuadro **nombre** , escriba **LinqDataManipulationApp**.  
  
5. Haga clic en **OK**.  
  
## <a name="adding-linq-references-and-directives"></a>Agregar referencias y directivas LINQ  

 En este tutorial se usan ensamblados que podrían no estar instalados en el proyecto de forma predeterminada. Si `System.Data.Linq` no aparece como referencia en el proyecto (haga clic en **Mostrar todos los archivos** en **Explorador de soluciones** y expanda el nodo **referencias** ), agréguelo, como se explica en los pasos siguientes.  
  
#### <a name="to-add-systemdatalinq"></a>Para agregar System.Data.Linq  
  
1. En **Explorador de soluciones**, haga clic con el botón secundario en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2. En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
3. En el editor de código, agregue las siguientes directivas sobre **Module1**:  
  
     [!code-vb[DLinqWalk3VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#1)]  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Agregar el archivo de código de Northwind al proyecto  

 En estos pasos se asume que ha utilizado la herramienta SQLMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Para agregar el archivo de código de Northwind al proyecto  
  
1. En el menú **Proyecto** , haga clic en **Agregar elemento existente**.  
  
2. En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest2\northwind.VB y, a continuación, haga clic en **Agregar**.  
  
     El archivo northwind.vb se agrega al proyecto.  
  
## <a name="setting-up-the-database-connection"></a>Configurar la conexión a la base de datos  

 Primero, pruebe su conexión a la base de datos. Observe en particular que el nombre de la base de datos, Northwnd, no tiene la i. Si se generan errores en los pasos siguientes, revise el archivo northwind.vb para determinar cómo se escribe el nombre de la clase parcial de Northwind.  
  
#### <a name="to-set-up-and-test-the-database-connection"></a>Para configurar y probar la conexión a la base de datos  
  
1. Escriba o pegue el código siguiente en la clase `Sub Main`:  
  
     [!code-vb[DLinqWalk3VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#2)]  
  
2. Presione F5 para probar la aplicación en este punto.  
  
     Se abre una ventana de **consola** .  
  
     Para cerrar la aplicación, presione Entrar en la ventana de la **consola** o haga clic en **detener depuración** en el menú **depurar** de Visual Studio.  
  
## <a name="creating-a-new-entity"></a>Crear una nueva entidad  

 Crear entidades es sencillo. Puede crear objetos (como `Customer`) mediante la palabra clave `New`.  
  
 En esta sección y las siguientes, realizará cambios solo en la memoria caché local. No se enviarán cambios a la base de datos hasta que llame a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, casi al final del tutorial.  
  
#### <a name="to-add-a-new-customer-entity-object"></a>Para agregar un nuevo objeto entidad Customer  
  
1. Cree un nuevo `Customer` agregando el código siguiente delante de `Console.ReadLine` en `Sub Main`:  
  
     [!code-vb[DLinqWalk3VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#3)]  
  
2. Presione F5 para depurar la solución.  
  
     Los resultados que se muestran en la ventana de la consola son los siguientes:  
  
     `Customers matching CA before insert:`  
  
     `Customer ID: CACTU`  
  
     `Customer ID: RICAR`  
  
     Observe que la nueva fila no aparece en los resultados. Los nuevos datos no se han enviado todavía a la base de datos.  
  
3. Presione entrar en la ventana de la **consola** para detener la depuración.  
  
## <a name="updating-an-entity"></a>Actualización de una entidad  

 En los pasos siguientes, recuperará un objeto `Customer` y modificará una de sus propiedades.  
  
#### <a name="to-change-the-name-of-a-customer"></a>Para cambiar el nombre de un cliente  
  
- Agregue el código siguiente encima de `Console.ReadLine()`:  
  
     [!code-vb[DLinqWalk3VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#4)]  
  
## <a name="deleting-an-entity"></a>Eliminación de una entidad  

 Con el mismo objeto de cliente, puede eliminar el primer pedido.  
  
 El código siguiente muestra cómo romper las relaciones entre las filas y cómo eliminar una fila de la base de datos.  
  
#### <a name="to-delete-a-row"></a>Para eliminar una fila  
  
- Agregue el código siguiente justo encima de `Console.ReadLine()`:  
  
     [!code-vb[DLinqWalk3VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#5)]  
  
## <a name="submitting-changes-to-the-database"></a>Enviar los cambios a la base de datos  

 El último paso necesario para crear, actualizar y eliminar objetos es realmente enviar los cambios a la base de datos. Sin este paso, los cambios se habrán realizado localmente y no aparecerán en los resultados de la consulta.  
  
#### <a name="to-submit-changes-to-the-database"></a>Para enviar los cambios a la base de datos  
  
1. Inserte el código siguiente justo encima de `Console.ReadLine`:  
  
     [!code-vb[DLinqWalk3VB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#6)]  
  
2. Inserte el código siguiente (después de `SubmitChanges`) para ver el antes y el después de enviar los cambios:  
  
     [!code-vb[DLinqWalk3VB#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk3VB/vb/Module1.vb#7)]  
  
3. Presione F5 para depurar la solución.  
  
     En la ventana de la consola aparece lo siguiente.  
  
    ```console
    Customers matching CA before update:  
    Customer ID: CACTU  
    Customer ID: RICAR  
  
    The Order Detail to be deleted is: OrderID = 10643  
  
    Customers matching CA after update:  
    Customer ID: A3VCA  
    Customer ID: CACTU  
    Customer ID: RICAR  
    ```  
  
4. Presione entrar en la ventana de la **consola** para detener la depuración.  
  
> [!NOTE]
> Después de haber agregado el nuevo cliente al enviar los cambios, no puede ejecutar de nuevo esta solución tal como está, porque no puede agregar el mismo cliente de nuevo tal como está. Para ejecutar de nuevo la solución, cambie el valor del identificador de cliente que se debe agregar.  
  
## <a name="see-also"></a>Consulte también

- [Aprender con tutoriales](learning-by-walkthroughs.md)
