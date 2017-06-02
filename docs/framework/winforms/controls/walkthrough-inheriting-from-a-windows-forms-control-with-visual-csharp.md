---
title: "Tutorial: Heredar de un control de formularios Windows Forms con Visual C# | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles personalizados [Windows Forms], herencia"
  - "herencia, control"
  - "herencia, controles personalizados"
  - "herencia, tutoriales"
  - "controles de Windows Forms, herencia"
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Tutorial: Heredar de un control de formularios Windows Forms con Visual C# #
[!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] permite crear controles personalizados eficaces mediante la *herencia*.  A través de la herencia, podrá crear controles que retengan toda la funcionalidad heredada de los controles estándar de formularios Windows Forms y que incorporen también funcionalidad personalizada.  En este tutorial, creará un control heredado sencillo denominado `ValueButton`.  Este botón heredará la funcionalidad del botón estándar del control <xref:System.Windows.Forms.Button> de los formularios Windows Forms y expondrá una propiedad personalizada denominada `ButtonValue`.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 Cuando cree un nuevo proyecto, debe especificar su nombre para establecer el espacio de nombres de la raíz, el nombre de ensamblado y el de proyecto, además de asegurarse de que el componente predeterminado estará en el espacio de nombres correcto.  
  
#### Para crear la biblioteca de controles ValueButtonLib y el control ValueButton  
  
1.  En el menú **Archivo**, elija **Nuevo** y, a continuación, haga clic en **Proyecto** para abrir el cuadro de diálogo **Nuevo proyecto**.  
  
2.  Seleccione la plantilla de proyecto **Biblioteca de controles de Windows Forms** en la lista de proyectos de [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] y escriba `ValueButtonLib` en el cuadro **Nombre**.  
  
     El nombre del proyecto, `ValueButtonLib`, se asigna también de forma predeterminada al espacio de nombres de la raíz.  El espacio de nombres de la raíz se utiliza para calificar los nombres de los componentes del ensamblado.  Por ejemplo, si dos ensamblados proporcionan componentes denominados `ValueButton`, puede especificar el componente `ValueButton` utilizando `ValueButtonLib.ValueButton`.  Para obtener más información, vea [Espacios de nombres](../Topic/Namespaces%20\(C%23%20Programming%20Guide\).md).  
  
3.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **UserControl1.cs** y, a continuación, elija **Cambiar nombre** en el menú contextual.  Cambie el nombre del archivo a `ValueButton.cs`.  Haga clic en el botón **Sí** cuando se le pregunte si desea cambiar el nombre de todas las referencias al elemento de código '`UserControl1`'.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **ValueButton.cs**, y seleccione **Ver código**.  
  
5.  Busque la línea de instrucción `class`, `public partial class ValueButton`, y cambie el tipo desde el que se hereda el control <xref:System.Windows.Forms.UserControl> a <xref:System.Windows.Forms.Button>.  Esta opción permite al control heredado heredar toda la funcionalidad del control <xref:System.Windows.Forms.Button>.  
  
6.  En el **Explorador de soluciones**, abra el nodo **ValueButton.cs** para mostrar el archivo de código generado por el diseñador, **ValueButton.Designer.cs**.  Abra este archivo en el **Editor de código**.  
  
7.  Busque el método `InitializeComponent` y quite la línea que asigna la propiedad <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.  Esta propiedad no existe en el control <xref:System.Windows.Forms.Button>.  
  
8.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
    > [!NOTE]
    >  Ya no hay ningún diseñador visual disponible.  Dado que el control <xref:System.Windows.Forms.Button> realiza su propia presentación, no podrá modificar su apariencia en el diseñador.  Su representación visual será exactamente la misma que la de la clase desde la que hereda \(es decir, <xref:System.Windows.Forms.Button>\) a menos que se modifique en el código.  Todavía puede agregar componentes, que no tengan ningún elemento de la interfaz de usuario, a la superficie de diseño.  
  
## Agregar una propiedad al control heredado  
 Uno de los usos posibles de los controles heredados de formularios Windows Forms es la creación de controles idénticos en la apariencia y en el funcionamiento a los controles estándar de formularios Windows Forms, pero que expongan propiedades personalizadas.  En esta sección, agregará al control una propiedad denominada `ButtonValue`.  
  
#### Para agregar la propiedad Value  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **ValueButton.cs** y, a continuación, haga clic en **Ver código** en el menú contextual.  
  
2.  Busque la instrucción `class`.  Inmediatamente después de `{`, escriba el siguiente código:  
  
     \[C\#\]  
  
    ```  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     Este código establece los métodos mediante los cuales se almacena y se recupera la propiedad `ButtonValue`.  La instrucción `get` establece el valor devuelto como el valor almacenado en la variable privada `varValue`, y la instrucción `set` establece el valor de la variable privada mediante el uso de la palabra clave `value`.  
  
3.  En el menú **Archivo**, elija **Guardar todo** para guardar el proyecto.  
  
## Probar el control  
 Los controles no son proyectos independientes; deben hospedarse en un contenedor.  Para probar el control, debe proporcionar un proyecto de prueba en el que ejecutarlo.  También debe compilar el control para hacerlo accesible al proyecto de prueba.  En esta sección, compilará el control y lo probará en Windows Forms.  
  
#### Para compilar el control  
  
1.  En el menú **Compilar**, haga clic en **Compilar solución**.  
  
     La generación debe ser correcta, sin errores ni advertencias del compilador.  
  
#### Para crear un proyecto de prueba  
  
1.  En el menú **Archivo**, elija **Agregar** y, a continuación, haga clic en **Nuevo proyecto** para abrir el cuadro de diálogo **Agregar nuevo proyecto**.  
  
2.  Seleccione el nodo **Windows**, bajo el nodo **Visual C\#**, y haga clic en **Aplicación de Windows Forms**.  
  
3.  En el cuadro **Nombre**, escriba `Test`.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nodo **Referencias** del proyecto de prueba y, a continuación, seleccione **Agregar referencia** en el menú contextual para mostrar el cuadro de diálogo **Agregar referencia**.  
  
5.  Haga clic en la ficha **Proyectos**.  El proyecto `ValueButtonLib` aparecerá en la lista **Nombre de proyecto**.  Haga doble clic en el proyecto para agregar la referencia al proyecto de prueba.  
  
6.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Test** y seleccione **Compilar**.  
  
#### Para agregar el control al formulario  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario en **Form1.cs** y elija **Diseñador de vistas** en el menú contextual.  
  
2.  En el **Cuadro de herramientas**, haga clic en **Componentes de ValueButtonLib**.  Haga doble clic en **ValueButton**.  
  
     Aparecerá un control **ValueButton** en el formulario.  
  
3.  Haga clic con el botón secundario en **ValueButton** y elija **Propiedades** en el menú contextual.  
  
4.  En la ventana **Propiedades**, examine las propiedades de este control.  Observe que son idénticas a las propiedades expuestas por un botón estándar, excepto en que hay una propiedad adicional, `ButtonValue`.  
  
5.  Establezca la propiedad `ButtonValue` en `5`.  
  
6.  En la ficha **Todos los formularios Windows Forms** del **Cuadro de herramientas**, haga doble clic en **Etiqueta** para agregar un control de <xref:System.Windows.Forms.Label> al formulario.  
  
7.  Coloque de nuevo la etiqueta en el centro del formulario.  
  
8.  Haga doble clic en `valueButton1`.  
  
     Se abrirá el **Editor de código** en el evento `valueButton1_Click`.  
  
9. Escriba la siguiente línea de código.  
  
     \[C\#\]  
  
    ```  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en **Test** y elija **Establecer como proyecto de inicio** en el menú contextual.  
  
11. En el menú **Depurar**, elija **Iniciar depuración**.  
  
     Aparece `Form1`.  
  
12. Haga clic en `valueButton1`.  
  
     Se muestra el número '5' en `label1`, que muestra que la propiedad `ButtonValue` del control heredado se ha pasado a `label1` mediante el método `valueButton1_Click`.  Así, el control `ValueButton` hereda toda la funcionalidad del botón estándar de formularios Windows Forms, pero expone una propiedad adicional, personalizada.  
  
## Vea también  
 [Programming with Components](../Topic/Programming%20with%20Components.md)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)   
 [Cómo: Mostrar un control en el cuadro de diálogo Elegir elementos de cuadro de herramientas](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [Tutorial: Crear un control compuesto con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)