---
title: 'Tutorial: Usar solo procedimientos almacenados (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 5a736a30-ba66-4adb-b87c-57d19476e862
ms.openlocfilehash: 57ae5dba89a299365e1ce3c2d54d844da0102f31
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163953"
---
# <a name="walkthrough-using-only-stored-procedures-visual-basic"></a>Tutorial: Usar solo procedimientos almacenados (Visual Basic)

Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos utilizando procedimientos almacenados solamente. Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.  
  
> [!NOTE]
> También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`. Para obtener más información, vea [personalizar las operaciones de inserción, actualización y eliminación](customizing-insert-update-and-delete-operations.md).  
  
 En este tutorial, utilizará dos métodos asignados a procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist. La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para generar un archivo de Visual Basic. Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.  
  
 Este tutorial no se basa en el Object Relational Designer. Los desarrolladores que usan Visual Studio también pueden usar O/R Designer para implementar la funcionalidad de procedimientos almacenados. Consulte [LINQ to SQL herramientas en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual Basic.  
  
## <a name="prerequisites"></a>Prerrequisitos  

 En este tutorial se requiere lo siguiente:  
  
- Este tutorial utiliza una carpeta dedicada ("c:\linqtest3") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
- Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [Descargar bases de datos de ejemplo](downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest3.  
  
- Archivo de código de Visual Basic generado a partir de la base de datos Northwind.  
  
     Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:  
  
     **sqlmetal /code:"c:\linqtest3\northwind.vb" /language:vb "c:\linqtest3\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Información general  

 Este tutorial se compone de seis tareas principales:  
  
- Configuración de la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.  
  
- Agregar el ensamblado System.Data.Linq al proyecto.  
  
- Agregar el archivo de código de la base de datos al proyecto.  
  
- Crear una conexión con la base de datos.  
  
- Configurar la interfaz de usuario.  
  
- Ejecutar y probar la aplicación.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Crear una solución LINQ to SQL  

 En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.  
  
### <a name="to-create-a-linq-to-sql-solution"></a>Para crear una solución LINQ to SQL  
  
1. En el menú **Archivo** de Visual Studio, haga clic en **Nuevo proyecto**.  
  
2. En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto** , expanda **Visual Basic**y, a continuación, haga clic en **Windows**.  
  
3. En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.  
  
4. En el cuadro **nombre** , escriba **SprocOnlyApp**.  
  
5. Haga clic en **OK**.  
  
     Se abre el Diseñador de Windows Forms.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Agregar la referencia al ensamblado de LINQ to SQL  

 El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar. Tendrá que agregar el ensamblado como se explica en los pasos siguientes:  
  
### <a name="to-add-systemdatalinqdll"></a>Para agregar System.Data.Linq.dll  
  
1. En **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**.  
  
2. En **Explorador de soluciones**, haga clic con el botón secundario en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
3. En el cuadro de diálogo **Agregar referencia** , haga clic en **.net**, haga clic en el ensamblado System. Data. Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Agregar el archivo de código de Northwind al proyecto  

 En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
### <a name="to-add-the-northwind-code-file-to-the-project"></a>Para agregar el archivo de código de Northwind al proyecto  
  
1. En el menú **Proyecto** , haga clic en **Agregar elemento existente**.  
  
2. En el cuadro de diálogo **Agregar elemento existente** , desplácese a c:\linqtest3\northwind.VB y, a continuación, haga clic en **Agregar**.  
  
     El archivo northwind.vb se agrega al proyecto.  
  
## <a name="creating-a-database-connection"></a>Crear una conexión de base de datos  

 En este paso, definirá la conexión con la base de datos de ejemplo Northwind. En este tutorial se utiliza "c:\linqtest3\northwnd.mdf" como ruta de acceso.  
  
### <a name="to-create-the-database-connection"></a>Para crear la conexión a la base de datos  
  
1. En **Explorador de soluciones**, haga clic con el botón secundario en **Form1. VB**y, a continuación, haga clic en **Ver código**.  
  
     `Class Form1` aparece en el editor de código.  
  
2. Escriba el código siguiente en el bloque de código `Form1`:  
  
     [!code-vb[DLinqWalk4VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#1)]  
  
## <a name="setting-up-the-user-interface"></a>Configurar la interfaz de usuario  

 En esta tarea creará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos. En la aplicación que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.  
  
### <a name="to-set-up-the-user-interface"></a>Para configurar la interfaz de usuario  
  
1. Vuelva al Diseñador de Windows Forms (**Form1. VB [diseño]**).  
  
2. En el menú **Ver** , haga clic en **Cuadro de herramientas**.  
  
     Se abrirá el cuadro de herramientas.  
  
    > [!NOTE]
    > Haga clic en el marcador **Ocultar automáticamente** para mantener el cuadro de herramientas abierto mientras realiza los pasos restantes de esta sección.  
  
3. Arrastre dos botones, dos cuadros de texto y dos etiquetas desde el cuadro de herramientas hasta **Form1**.  
  
     Organice los controles como en la ilustración anexa. Expanda **Form1** para que los controles se ajusten fácilmente.  
  
4. Haga clic con el botón secundario en **Label1**y, a continuación, haga clic en **propiedades**.  
  
5. Cambie la propiedad **Text** de **Label1** a **Enter OrderID:**.  
  
6. Del mismo modo para **Label2**, cambie la propiedad **Text** de **Label2** a **Enter CustomerID:**.  
  
7. Del mismo modo, cambie la propiedad **Text** de **button1** a **Order Details**.  
  
8. Cambie la propiedad **Text** de **BUTTON2** a **Order History**.  
  
     Amplíe los controles de botón para que todo el texto esté visible.  
  
### <a name="to-handle-button-clicks"></a>Para administrar los clics de botón  
  
1. Haga doble clic en **Order Details** en **Form1** para crear el `Button1` controlador de eventos y abrir el editor de código.  
  
2. Escriba el código siguiente en el controlador `Button1`:  
  
     [!code-vb[DLinqWalk4VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#2)]  
  
3. Ahora haga doble clic en **BUTTON2** en Form1 para crear el `Button2` controlador de eventos y abrir el editor de código.  
  
4. Escriba el código siguiente en el controlador `Button2`:  
  
     [!code-vb[DLinqWalk4VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk4VB/vb/Form1.vb#3)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  

 Ha llegado el momento de probar la aplicación. Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados. Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.  
  
### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1. Presiona F5 para iniciar la depuración.  
  
     Aparece Form1.  
  
2. En el cuadro **Enter OrderID** , escriba **10249** y, a continuación, haga clic en **Order Details**.  
  
     Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
3. En el cuadro **Escriba CustomerID** , escriba `ALFKI` y, a continuación, haga clic en **historial de pedidos**.  
  
     Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
4. En el cuadro **Enter OrderID** , escriba `123` y, a continuación, haga clic en **Order Details**.  
  
     Aparece un cuadro de mensaje con el texto "No results".  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
5. En el menú **depurar** , haga clic en **detener depuración**.  
  
     La sesión de depuración se cierra.  
  
6. Si ha terminado de experimentar, puede hacer clic en **cerrar proyecto** en el menú **archivo** y guardar el proyecto cuando se le solicite.  
  
## <a name="next-steps"></a>Pasos siguientes  

 Puede mejorar este proyecto realizando algunos cambios. Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar. También podría transmitir el resultado de los informes a un archivo de texto.  
  
## <a name="see-also"></a>Consulte también

- [Aprender con tutoriales](learning-by-walkthroughs.md)
- [Procedimientos almacenados](stored-procedures.md)
