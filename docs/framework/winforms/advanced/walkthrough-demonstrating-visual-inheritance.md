---
title: "Tutorial: Demostraci&#243;n de la herencia visual | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "herencia de formularios, tutoriales"
  - "herencia, tutoriales"
  - "herencia visual"
  - "tutoriales [Windows Forms], herencia visual"
  - "Windows Forms, herencia"
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Tutorial: Demostraci&#243;n de la herencia visual
La herencia visual le permite ver los controles del formulario base y agregar controles nuevos.  En este tutorial, creará un formulario base y lo compilará para convertirlo en una biblioteca de clases.  Importará la biblioteca de clases en otro proyecto y creará un nuevo formulario que herede del formulario base.  Durante este tutorial aprenderá a:  
  
-   Crear un proyecto de biblioteca de clases que contiene un formulario base.  
  
-   Agregar un botón con propiedades que las clases derivadas del formulario base pueden modificar.  
  
-   Agregar un botón que los herederos del formulario base no pueden modificar.  
  
-   Crear un proyecto que contiene un formulario que hereda de `BaseForm`.  
  
 Por último, en este tutorial se mostrará la diferencia entre los controles privados y los protegidos de un formulario heredado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!CAUTION]
>  No todos los controles admiten la herencia visual a partir de un formulario base.  Los siguientes controles no admiten el escenario que se describe en este tutorial:  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  Estos controles del formulario heredado siempre son de solo lectura, independientemente de los modificadores que utilice \(`private`, `protected` o `public`\).  
  
## Pasos del escenario  
 El primer paso es crear el formulario base.  
  
#### Para crear un proyecto de biblioteca de clases que contenga un formulario base  
  
1.  En el menú **Archivo**, elija **Nuevo** y, luego, elija **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Cree una aplicación de Windows Forms llamada `BaseFormLibrary`.  
  
3.  Para crear una biblioteca de clases en lugar de una aplicación de Windows Forms estándar, en el **Explorador de soluciones**, haga clic con el botón derecho en el nodo de proyecto **BaseFormLibrary** y, después, elija **Propiedades**.  
  
4.  En las propiedades del proyecto, cambie el **Tipo de resultado** de **Aplicación Windows** a **Biblioteca de clases**.  
  
5.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto y los archivos en la ubicación predeterminada.  
  
 Los dos procedimientos siguientes agregan botones al formulario base.  Para ilustrar la herencia visual, proporcionará a los botones distintos niveles de acceso estableciendo sus propiedades `Modifiers`.  
  
#### Para agregar un botón que los herederos del formulario base puedan modificar  
  
1.  Abra **Form1** en el diseñador.  
  
2.  En la pestaña **Todos los formularios Windows Forms** del **Cuadro de herramientas**, haga doble clic en **Botón** para agregar un botón al formulario.  Use el mouse para colocar y cambiar de tamaño el botón.  
  
3.  En la ventana Propiedades, establezca las propiedades siguientes del botón:  
  
    -   Establezca la propiedad **Text** como **Decir hola**.  
  
    -   Establezca la propiedad **\(Name\)** como **btnProtected**.  
  
    -   Establezca la propiedad **Modifiers** como **Protected**.  Esto permite que los formularios que heredan de **Form1** modifiquen las propiedades de **btnProtected**.  
  
4.  Haga doble clic en el botón **Decir hola** para agregar un controlador de eventos para el evento **Click**.  
  
5.  Agregue la línea de código siguiente al controlador del evento:  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### Para agregar un botón que los herederos del formulario base no puedan modificar  
  
1.  Pase a la vista Diseño haciendo clic en la pestaña **Form1.vb \[Diseño\], Form1.cs \[Diseño\] o Form1.jsl \[Diseño\]** encima del editor de código o presionando F7.  
  
2.  Agregue un segundo botón y establezca sus propiedades como sigue:  
  
    -   Establezca la propiedad **Text** como **Decir adiós**.  
  
    -   Establezca la propiedad **\(Name\)** como **btnPrivate**.  
  
    -   Establezca la propiedad **Modifiers** como **Private**.  Esto impide que los formularios que heredan de **Form1** modifiquen las propiedades de **btnPrivate**.  
  
3.  Haga doble clic en el botón **Decir adiós** para agregar un controlador de eventos para el evento **Click**.  Coloque la siguiente línea de código en el procedimiento de evento:  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  En el menú **Compilación**, elija **Compilar biblioteca BaseForm** para compilar la biblioteca de clases.  
  
     Una vez compilada la biblioteca, puede crear un nuevo proyecto que herede del formulario que acaba de crear.  
  
#### Para crear un proyecto que contenga un formulario que herede del formulario base  
  
1.  En el menú **Archivo**, elija **Agregar** y, luego, elija **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.  
  
2.  Cree una aplicación de Windows Forms llamada `InheritanceTest`.  
  
#### Para agregar un formulario heredado  
  
1.  En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest**, elija **Agregar** y, luego, elija **Nuevo elemento**.  
  
2.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione la categoría **Windows Forms** \(si aparece una lista de categorías\) y, después, seleccione la plantilla **Formulario heredado**.  
  
3.  Deje el nombre predeterminado de `Form2` y haga clic en **Agregar**.  
  
4.  En el cuadro de diálogo **Selector de herencia**, elija **Form1** desde el proyecto **BaseFormLibrary** como el formulario del que se heredará y haga clic en **Aceptar**.  
  
     Se creará un formulario en el proyecto **InheritanceTest** que derivará del formulario de **BaseFormLibrary**.  
  
5.  Abra el formulario heredado \(**Form2**\) en el diseñador haciendo doble clic en él, si no está abierto ya.  
  
     En el diseñador, los botones heredados tienen un símbolo \(![Captura de pantalla de VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\) en la esquina superior para indicar que son heredados.  
  
6.  Elija el botón **Decir hola** y observe los controladores de tamaño.  Como este botón está protegido, los herederos pueden moverlo, cambiarlo de tamaño, cambiar su descripción y realizar otras modificaciones.  
  
7.  Elija el botón privado **Decir adiós** y observe que no tiene controladores de tamaño.  Además, en la ventana **Propiedades**, las propiedades del botón aparecen en gris para indicar que no se pueden modificar.  
  
8.  Si está utilizando [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]:  
  
    1.  En el **Explorador de soluciones**, haga clic con el botón derecho en **Form1** en el proyecto **InheritanceTest** y, luego, elija **Eliminar**.  En el cuadro de mensaje que aparece, haga clic en **Aceptar** para confirmar la eliminación.  
  
    2.  Abra el archivo Program.cs y cambie la línea `Application.Run(new Form1());` por `Application.Run(new Form2());`.  
  
9. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y elija **Establecer como proyecto de inicio**.  
  
10. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **InheritanceTest** y elija **Propiedades**.  
  
11. En las páginas de propiedades de **InheritanceTest**, establezca el **Objeto de inicio** de modo que sea el formulario heredado \(**Form2**\).  
  
12. Presione F5 para ejecutar la aplicación y observe el comportamiento del formulario heredado.  
  
## Pasos siguientes  
 La herencia de los controles de usuario funciona más o menos de la misma manera.  Abra un proyecto nuevo de biblioteca de clases y agregue un control de usuario.  Coloque en él controles constituyentes y compile el proyecto.  Abra otro proyecto nuevo de biblioteca de clases y agregue una referencia a la biblioteca de clases compilada.  Además, pruebe a agregar al proyecto un control heredado \(con el cuadro de diálogo **Agregar nuevos elementos**\) y a usar el **Selector de herencia**.  Agregue un control de usuario y cambie la instrucción `Inherits` \(`:` en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\).  Para más información, consulte [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).  
  
## Vea también  
 [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Herencia visual de formularios Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)