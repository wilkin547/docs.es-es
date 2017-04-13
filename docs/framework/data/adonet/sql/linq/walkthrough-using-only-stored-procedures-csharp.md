---
title: "Tutorial: Usar solo procedimientos almacenados (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecde4bf2-fa4d-4252-b5e4-96a46b9e097d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Tutorial: Usar solo procedimientos almacenados (C#)
Este tutorial proporciona un escenario completo básico de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para tener acceso a los datos ejecutando procedimientos almacenados solamente.  Este enfoque suelen utilizarlo los administradores de bases de datos para limitar el acceso al almacén de datos.  
  
> [!NOTE]
>  También puede utilizar procedimientos almacenados en aplicaciones [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para invalidar el comportamiento predeterminado, especialmente para los procesos `Create`, `Update` y `Delete`.  Para obtener más información, consulte [Personalizar operaciones de actualización, inserción y eliminación](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
  
 En este tutorial, utilizará dos métodos asignados a procedimientos almacenados en la base de datos de ejemplo Northwind: CustOrdersDetail y CustOrderHist.  La asignación se produce al ejecutar la herramienta de línea de comandos SqlMetal para crear un archivo de C\#.  Para obtener más información, vea la sección Requisitos previos que se incluye posteriormente en este tutorial.  
  
 En este tutorial no se utiliza el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].  Los desarrolladores de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] también pueden utilizar el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] para implementar funcionalidad de procedimiento almacenado.  Consulte [LINQ to SQL Tools en Visual Studio](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio2.md).  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Este tutorial se escribió con la configuración de desarrollo de Visual C\#.  
  
## Requisitos previos  
 En este tutorial se requiere lo siguiente:  
  
-   Este tutorial utiliza una carpeta dedicada \("c:\\linqtest7"\) que contiene los archivos.  Cree esta carpeta antes de empezar el tutorial.  
  
-   Base de datos de ejemplo Northwind.  
  
     Si no dispone de esta base de datos en el equipo de desarrollo, puede descargarla del sitio web de descargas de Microsoft.  Para obtener más información, consulte [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).  Después de haber descargado la base de datos, copie el archivo northwnd.mdf en la carpeta c:\\linqtest7.  
  
-   Un archivo de código de C\# generado a partir de la base de datos Northwind.  
  
     Este tutorial se escribió utilizando la herramienta SqlMetal con la línea de comandos siguiente:  
  
     **sqlmetal \/code:"c:\\linqtest7\\northwind.cs" \/language:csharp "c:\\linqtest7\\northwnd.mdf" \/sprocs \/functions \/pluralize**  
  
     Para obtener más información, consulte [SqlMetal.exe \(Herramienta de generación de código\)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## Información general  
 Este tutorial se compone de seis tareas principales:  
  
-   Configurar la solución de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] en [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)].  
  
-   Agregar el ensamblado System.Data.Linq al proyecto.  
  
-   Agregar el archivo de código de la base de datos al proyecto.  
  
-   Crear una conexión con la base de datos.  
  
-   Configurar la interfaz de usuario.  
  
-   Ejecutar y probar la aplicación.  
  
## Crear una solución LINQ to SQL  
 En esta primera tarea, va a crear una solución de [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] que contiene las referencias necesarias para compilar y ejecutar un proyecto de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
#### Para crear una solución LINQ to SQL  
  
1.  En el menú [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] de **Archivo**, elija **Nuevo** y, a continuación, haga clic en **Proyecto**.  
  
2.  En el panel **Tipos de proyecto** del cuadro de diálogo **Nuevo proyecto**, haga clic en **Visual C\#**.  
  
3.  En el panel **Plantillas**, haga clic en **Aplicación de Windows Forms**.  
  
4.  En el cuadro **Nombre**, escriba SprocOnlyApp.  
  
5.  En el cuadro **Ubicación**, compruebe dónde desea almacenar los archivos de proyecto.  
  
6.  Haga clic en **Aceptar**.  
  
     Se abre el Diseñador de Windows Forms.  
  
## Agregar la referencia al ensamblado de LINQ to SQL  
 El ensamblado de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no está incluido en la plantilla Aplicación de Windows Forms estándar.  Tendrá que agregar el ensamblado como se explica en los pasos siguientes:  
  
#### Para agregar System.Data.Linq.dll  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Referencias** y, a continuación, haga clic en **Agregar referencia**.  
  
2.  En el cuadro de diálogo **Agregar referencia**, haga clic en **.NET**, en el ensamblado System.Data.Linq y, a continuación, en **Aceptar**.  
  
     El ensamblado se agrega al proyecto.  
  
## Agregar el archivo de código de Northwind al proyecto  
 En este paso se asume que ha utilizado la herramienta SqlMetal para generar un archivo de código a partir de la base de datos de ejemplo Northwind.  Para obtener más información, vea la sección Requisitos previos, anteriormente en este tutorial.  
  
#### Para agregar el archivo de código de Northwind al proyecto  
  
1.  En el menú **Proyecto**, haga clic en **Agregar elemento existente**.  
  
2.  En el cuadro de diálogo **Agregar elemento existente**, vaya a la ubicación del archivo c:\\linqtest7\\northwind.cs y, a continuación, haga clic en **Agregar**.  
  
     El archivo northwind.cs se agrega al proyecto.  
  
## Crear una conexión de base de datos  
 En este paso, definirá la conexión con la base de datos de ejemplo Northwind.  En este tutorial se utiliza "c:\\linqtest7\\northwnd.mdf" como ruta de acceso.  
  
#### Para crear la conexión a la base de datos  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Form1.cs** y, a continuación, en **Ver código**.  
  
2.  Escriba el código siguiente en la clase `Form1`:  
  
     [!code-csharp[DLinqWalk4CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#1)]  
  
## Configurar la interfaz de usuario  
 En esta tarea preparará una interfaz para que los usuarios puedan ejecutar procedimientos almacenados para tener acceso a los datos de la base de datos.  En las aplicaciones que desarrolla con este tutorial, los usuarios pueden tener acceso a los datos de la base de datos únicamente mediante los procedimientos almacenados que están incrustados en la aplicación.  
  
#### Para configurar la interfaz de usuario  
  
1.  Regrese al Diseñador de Windows Forms \(**Form1.cs\[Design\]**\).  
  
2.  En el menú **Ver**, haga clic en **Cuadro de herramientas**.  
  
     Se abrirá el cuadro de herramientas.  
  
    > [!NOTE]
    >  Haga clic en el icono para **ocultar automáticamente** de forma que el cuadro de herramientas se mantenga abierto mientras realiza los demás pasos de esta sección.  
  
3.  Arrastre dos botones, dos cuadros de texto y dos etiquetas desde el cuadro de herramientas hasta **Form1**.  
  
     Organice los controles como en la ilustración anexa.  Expanda **Form1** para que los controles tengan el espacio necesario.  
  
4.  Haga clic con el botón secundario del mouse en **label1** y, a continuación, haga clic en **Propiedades**.  
  
5.  Cambie la propiedad de **texto** de **label1** a **Enter OrderID:**.  
  
6.  De la misma manera, para **label2**, cambie la propiedad de **texto** de **label2** a **Enter CustomerID:**.  
  
7.  De la misma manera, cambie la propiedad de **texto** de **button1** a **Order Details**.  
  
8.  Cambie la propiedad de **texto** para **button2** a **Order History**.  
  
     Amplíe los controles de botón para que todo el texto esté visible.  
  
#### Para administrar los clics de botón  
  
1.  Haga doble clic en **Order Details** en **Form1** para abrir el controlador de eventos button1 en el editor de código.  
  
2.  Escriba el código siguiente en el controlador `button1`:  
  
     [!code-csharp[DLinqWalk4CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#2)]  
  
3.  Ahora, haga doble clic en **button2** en **Form1** para abrir el controlador `button2`.  
  
4.  Escriba el código siguiente en el controlador `button2`:  
  
     [!code-csharp[DLinqWalk4CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk4CS/cs/Form1.cs#3)]  
  
## Probar la aplicación  
 Ha llegado el momento de probar la aplicación.  Observe que su contacto con el almacén de datos se limita a las acciones que puedan realizar los dos procedimientos almacenados.  Esas acciones son: devolver los productos incluidos para cualquier orderID que escriba o devolver un historial de los productos solicitados para cualquier CustomerID que escriba.  
  
#### Para probar la aplicación  
  
1.  Presione F5 para iniciar la depuración.  
  
     Aparece Form1.  
  
2.  En el cuadro **Enter OrderID**, escriba `10249` y, a continuación, haga clic en **Order Details**.  
  
     Un cuadro de mensaje muestra los productos incluidos en el pedido 10249.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
3.  En el cuadro **Enter CustomerID**, escriba `ALFKI` y, a continuación, haga clic en **Order History**.  
  
     Aparece un cuadro de mensaje con el historial de pedidos del cliente ALFKI.  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
4.  En el cuadro **Enter OrderID**, escriba `123` y, a continuación, haga clic en **Order Details**.  
  
     Aparece un cuadro de mensaje con el texto "No results".  
  
     Haga clic en **Aceptar** para cerrar el cuadro de mensaje.  
  
5.  En el menú **Depurar**, haga clic en **Detener depuración**.  
  
     La sesión de depuración se cierra.  
  
6.  Cuando termine de experimentar, haga clic en **Cerrar proyecto** en el menú **Archivo** y guarde su proyecto cuando se le solicite.  
  
## Pasos siguientes  
 Puede mejorar este proyecto realizando algunos cambios.  Por ejemplo, podría enumerar los procedimientos almacenados disponibles en un cuadro de lista y permitir que el usuario seleccione qué procedimientos debe ejecutar.  También podría transmitir el resultado de los informes a un archivo de texto.  
  
## Vea también  
 [Aprender mediante tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)   
 [Procedimientos almacenados](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)