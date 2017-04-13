---
title: "Soluci&#243;n de problemas relacionados con la creaci&#243;n de controles y componentes | Microsoft Docs"
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
  - "componentes [Windows Forms], solucionar problemas"
  - "controles [Windows Forms], solucionar problemas"
  - "solucionar problemas de componentes"
  - "solucionar problemas de controles"
  - "controles de Windows Forms, depurar"
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Soluci&#243;n de problemas relacionados con la creaci&#243;n de controles y componentes
Este tema enumera los siguientes problemas comunes que surgen cuando se desarrollan componentes y controles.  Para obtener más información, vea [Programming with Components](../Topic/Programming%20with%20Components.md).  
  
-   No se puede agregar un control al Cuadro de herramientas  
  
-   No se puede depurar un componente o control de usuario de formularios Windows Forms  
  
-   Un evento se produce dos veces en un control o componente heredado  
  
-   Error en tiempo de diseño: "Error al crear el componente '*Nombre de componente*'"  
  
-   STAThreadAttribute  
  
-   El icono del componente no aparece en el cuadro de herramientas  
  
## No se puede agregar un control al Cuadro de herramientas  
 Si desea agregar un control personalizado que haya creado en otro proyecto o un control de otro fabricante al **Cuadro de herramientas**, debe hacerlo manualmente.  Si el proyecto actual contiene el control o componente, debería aparecer automáticamente en el **Cuadro de herramientas**.  Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
#### Para agregar un control al Cuadro de herramientas  
  
1.  Haga clic con el botón secundario del mouse en el **Cuadro de herramientas** y, en el menú contextual, seleccione **Elegir elementos**.  
  
2.  En el cuadro de diálogo **Elegir elementos del cuadro de herramientas**, agregue el componente:  
  
    -   Si desea agregar un componente o control .NET Framework, haga clic en la ficha **Componentes de .NET Framework**.  
  
         O bien  
  
    -   Si desea agregar un componente COM o un control ActiveX, haga clic en la ficha **Componentes COM**.  
  
3.  Si el control aparece en el cuadro de diálogo, asegúrese de que está seleccionado y haga clic en **Aceptar**.  
  
     Ya ha agregado el control al **Cuadro de herramientas**.  
  
4.  Si el control no aparece en el cuadro de diálogo, proceda como se indica a continuación:  
  
    1.  Haga clic en el botón **Examinar**.  
  
    2.  Busque la carpeta que contiene el archivo .dll que contiene el control.  
  
    3.  Seleccione el archivo .dll y haga clic en **Abrir**.  
  
         El control aparece ahora en el cuadro de diálogo.  
  
    4.  Confirme que el control está seleccionado, y, a continuación, haga clic en **Aceptar**.  
  
         Ya ha agregado el control al **Cuadro de herramientas**.  
  
## No se puede depurar un componente o control de usuario de formularios Windows Forms  
 Si el control deriva de la clase <xref:System.Windows.Forms.UserControl>, puede depurar su comportamiento en tiempo de ejecución con el contenedor de prueba.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Los demás componentes y controles personalizados no son proyectos independientes.  Deben estar hospedados en una aplicación como un proyecto de formularios Windows Forms.  Para depurar un control o componente, debe agregarlo a un proyecto de formularios Windows Forms.  
  
#### Para depurar un control o componente  
  
1.  En el menú **Compilar**, haga clic en **Compilar solución** para compilar la solución.  
  
2.  En el menú **Archivo**, elija **Agregar** y, a continuación, seleccione **Nuevo proyecto** para agregar un proyecto de prueba a la aplicación.  
  
3.  En el cuadro de diálogo **Agregar nuevo proyecto**, elija **Aplicación para Windows** como tipo de proyecto.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nodo **Referencias** para el nuevo proyecto.  En el menú contextual, haga clic en **Agregar referencia** para agregar una referencia al proyecto que contiene el control o componente.  
  
5.  Cree una instancia del control o componente en el proyecto de prueba.  Si el componente está en el **Cuadro de herramientas**, puede arrastrarlo hasta la superficie de diseño; o bien, puede crear la instancia mediante programación como se muestra en el ejemplo siguiente:  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     Ahora puede depurar el control o componente con siempre.  
  
 Para obtener más información sobre depuración, vea [Depurar en Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md) y [Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
## Un evento se produce dos veces en un control o componente heredado  
 Probablemente, esto se debe a una cláusula `Handles` duplicada.  Para obtener más información, vea [Solucionar problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md).  
  
## Error en tiempo de diseño: "Error al crear el componente 'Nombre de componente'"  
 El componente o control debe proporcionar un constructor predeterminado sin parámetros.  Cuando el entorno de diseño crea una instancia del componente o control, no intenta proporcionar ningún parámetro a la sobrecarga del constructor que toma parámetros.  
  
## STAThreadAttribute  
 <xref:System.STAThreadAttribute> informa a Common Language Runtime \(CLR\) que Windows Forms utiliza el modelo de contenedor uniproceso.  Puede observar un comportamiento imprevisto si no aplica este atributo al método `Main` de la aplicación de Windows Forms.  Por ejemplo, es posible que no aparezcan las imágenes de fondo en controles como <xref:System.Windows.Forms.ListView>.  Algunos controles también pueden requerir este atributo para corregir el comportamiento de Autocompletar y de arrastrar y colocar.  
  
## El icono del componente no aparece en el cuadro de herramientas  
 Cuando se usa <xref:System.Drawing.ToolboxBitmapAttribute> para asociar un icono a un componente personalizado, el mapa de bits no aparece en el cuadro de herramientas para los componentes generados automáticamente.  Para ver el mapa de bits, recargue el control mediante el cuadro de diálogo **Elegir elementos del cuadro de herramientas**.  Para obtener más información, vea [Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).  
  
## Vea también  
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)   
 [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)   
 [Tutorial: Depurar controles personalizados de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)   
 [Component Authoring](../Topic/Component%20Authoring.md)   
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [Programming with Components](../Topic/Programming%20with%20Components.md)