---
title: 'Tutorial: Usar solo procedimientos almacenados (C#)'
ms.date: 03/30/2017
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
ms.openlocfilehash: f16cbdc1d22e7ec08237c0f13db9499ee2f9194f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742552"
---
# <a name="walkthrough-using-only-stored-procedures-c"></a>Tutorial: Usar solo procedimientos almacenados (C#)
Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos ejecutando procedimientos almacenados solamente. Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.  
  
> [!NOTE]
>  También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`. Para obtener más información, consulte [personalizar Insert, Update y las operaciones de eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 Para fines de este tutorial, utilizará dos métodos que se han asignado a los procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist. La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para crear un archivo de C#. Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.  
  
 En este tutorial no se basa en Object Relational Designer. Los desarrolladores que usan Visual Studio también pueden usar el Object Relational Designer para implementar la funcionalidad de procedimiento almacenado. Consulte [LINQ to SQL Tools en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C#.  
  
## <a name="prerequisites"></a>Requisitos previos  
 En este tutorial se requiere lo siguiente:  
  
- Este tutorial utiliza una carpeta dedicada ("c:\linqtest7") que contiene los archivos. Cree esta carpeta antes de empezar el tutorial.  
  
- Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md). Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\linqtest7.  
  
- Un archivo de código de C# generado a partir de la base de datos Northwind.  
  
     Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:  
  
     **sqlmetal /code:"c:\linqtest7\northwind.cs" /language:csharp "c:\linqtest7\northwnd.mdf" /sprocs /functions /pluralize**  
  
     Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="overview"></a>Información general  
 Este tutorial se compone de seis tareas principales:  
  
- Configurar la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solución en Visual Studio.  
  
- Agregar el ensamblado System.Data.Linq al proyecto.  
  
- Agregar el archivo de código de la base de datos al proyecto.  
  
- Crear una conexión con la base de datos.  
  
- Configurar la interfaz de usuario.  
  
- Ejecutar y probar la aplicación.  
  
## <a name="creating-a-linq-to-sql-solution"></a>Crear una solución LINQ to SQL  
 En esta primera tarea, creará una solución de Visual Studio que contiene las referencias necesarias para compilar y ejecutar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proyecto.  
  
#### <a name="to-create-a-linq-to-sql-solution"></a>Para crear una solución LINQ to SQL  
  
1. En Visual Studio **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.  
  
2. En el **tipos de proyecto** panel en el **nuevo proyecto** cuadro de diálogo, haga clic en **Visual C#** .  
  
3. En el panel **Plantillas** , haga clic en **Aplicación de Windows Forms**.  
  
4. En el **nombre** , escriba **SprocOnlyApp**.  
  
5. En el **ubicación** Compruebe dónde desea almacenar los archivos de proyecto.  
  
6. Haga clic en **OK**.  
  
     Se abre el Diseñador de Windows Forms.  
  
## <a name="adding-the-linq-to-sql-assembly-reference"></a>Agregar la referencia al ensamblado de LINQ to SQL  
 El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar. Tendrá que agregar el ensamblado como se explica en los pasos siguientes:  
  
#### <a name="to-add-systemdatalinqdll"></a>Para agregar System.Data.Linq.dll  
  
1. En **el Explorador de soluciones**, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.  
  
2. En el **Agregar referencia** cuadro de diálogo, haga clic en **.NET**, haga clic en el ensamblado System.Data.Linq y, a continuación, haga clic en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
## <a name="adding-the-northwind-code-file-to-the-project"></a>Agregar el archivo de código de Northwind al proyecto  
 En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind. Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
#### <a name="to-add-the-northwind-code-file-to-the-project"></a>Para agregar el archivo de código de Northwind al proyecto  
  
1. En el **proyecto** menú, haga clic en **Agregar elemento existente**.  
  
2. En el **Agregar elemento existente** cuadro de diálogo Mover a c:\linqtest7\northwind.cs y, a continuación, haga clic en **agregar**.  
  
     El archivo northwind.cs se agrega al proyecto.  
  
## <a name="creating-a-database-connection"></a>Crear una conexión de base de datos  
 En este paso, definirá la conexión con la base de datos de ejemplo Northwind. En este tutorial se utiliza "c:\linqtest7\northwnd.mdf" como ruta de acceso.  
  
#### <a name="to-create-the-database-connection"></a>Para crear la conexión a la base de datos  
  
1. En **el Explorador de soluciones**, haga clic en **Form1.cs**y, a continuación, haga clic en **ver código**.  
  
2. Escriba el código siguiente en la clase `Form1`:  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## <a name="setting-up-the-user-interface"></a>Configurar la interfaz de usuario  
 En esta tarea preparará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos. En las aplicaciones que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.  
  
#### <a name="to-set-up-the-user-interface"></a>Para configurar la interfaz de usuario  
  
1. Diseñador de vuelta a la Windows Forms (**Form1.cs [Diseño]** ).  
  
2. En el menú **Ver** , haga clic en **Cuadro de herramientas**.  
  
     Se abrirá el cuadro de herramientas.  
  
    > [!NOTE]
    >  Haga clic en el **Ocultar automáticamente** chincheta para mantener el cuadro de herramientas abierto mientras realiza los demás pasos de esta sección.  
  
3. Arrastre dos etiquetas, dos cuadros de texto y dos botones del cuadro de herramientas **Form1**.  
  
     Organice los controles como en la ilustración anexa. Expanda **Form1** para que los controles se ajustan fácilmente.  
  
4. Haga clic en **label1**y, a continuación, haga clic en **propiedades**.  
  
5. Cambiar el **texto** propiedad desde **label1** a **Enter OrderID:** .  
  
6. En la misma manera para **label2**, cambie el **texto** propiedad desde **label2** a **Enter CustomerID:** .  
  
7. En la misma manera, cambie el **texto** propiedad **button1** a **Order Details**.  
  
8. Cambiar el **texto** propiedad **button2** a **historial de pedidos**.  
  
     Amplíe los controles de botón para que todo el texto esté visible.  
  
#### <a name="to-handle-button-clicks"></a>Para administrar los clics de botón  
  
1. Haga doble clic en **Order Details** en **Form1** para abrir el controlador de eventos button1 en el editor de código.  
  
2. Escriba el código siguiente en el controlador `button1`:  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3. Ahora haga doble clic en **button2** en **Form1** para abrir el `button2` controlador  
  
4. Escriba el código siguiente en el controlador `button2`:  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Ha llegado el momento de probar la aplicación. Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados. Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.  
  
#### <a name="to-test-the-application"></a>Para probar la aplicación  
  
1. Presiona F5 para iniciar la depuración.  
  
     Aparece Form1.  
  
2. En el **Enter OrderID** , escriba `10249`y, a continuación, haga clic en **Order Details**.  
  
     Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
3. En el **Enter CustomerID** , escriba `ALFKI`y, a continuación, haga clic en **historial de pedidos**.  
  
     Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
4. En el **Enter OrderID** , escriba `123`y, a continuación, haga clic en **Order Details**.  
  
     Aparece un cuadro de mensaje con el texto "No results".  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
5. En el **depurar** menú, haga clic en **detener la depuración**.  
  
     La sesión de depuración se cierra.  
  
6. Si ha terminado de experimentar, haga clic en **cerrar proyecto** en el **archivo** menú y guarde el proyecto cuando se le pida.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Puede mejorar este proyecto realizando algunos cambios. Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar. También podría transmitir el resultado de los informes a un archivo de texto.  
  
## <a name="see-also"></a>Vea también

- [Aprendizaje con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
