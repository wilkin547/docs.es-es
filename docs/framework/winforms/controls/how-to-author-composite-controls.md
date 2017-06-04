---
title: "C&#243;mo: Crear controles compuestos | Microsoft Docs"
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
  - "controles compuestos, crear"
  - "controles de usuario [Windows Forms], crear"
  - "controles de usuario [Windows Forms], heredar"
  - "UserControl (clase), crear controles compuestos"
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear controles compuestos
Los controles compuestos pueden emplearse de muchas formas.  Puede crearlos como parte de un proyecto de aplicación para escritorio de Windows y utilizarlos sólo como formularios del proyecto.  También podría crearlos en un proyecto de Biblioteca de controles de Windows, compilar el proyecto en un ensamblado y utilizar los controles en otros proyectos.  Es posible incluso heredar de ellos y utilizar la herencia visual para personalizarlos rápidamente para fines especiales.  
  
> [!NOTE]
>  Si desea crear un control compuesto para utilizarlo en los formularios Web Forms, vea [Developing Custom ASP.NET Server Controls](../Topic/Developing%20Custom%20ASP.NET%20Server%20Controls.md).  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un control compuesto  
  
1.  Abra un nuevo proyecto **Aplicación para Windows** denominado `DemoControlHost`.  
  
2.  En el menú **Proyecto**, haga clic en **Agregar control de usuario**.  
  
3.  En el cuadro de diálogo **Agregar nuevo elemento**, dé al archivo de clase \(archivo .vb o .cs\) el nombre que desea para el control compuesto.  
  
4.  Haga clic en el botón **Agregar** para crear el archivo de clase para el control compuesto.  
  
5.  Agregue controles del **Cuadro de herramientas** a la superficie del control compuesto.  
  
6.  Escriba código en los procedimientos de evento para controlar los eventos que produzca el control compuesto o sus controles constituyentes.  
  
7.  Cierre el diseñador para el control compuesto y guarde el archivo cuando se le indique.  
  
8.  En el menú **Compilar**, haga clic en **Compilar solución**.  
  
     Para que los controles personalizados aparezcan en el **Cuadro de herramientas**, deberá compilar el proyecto.  
  
9. Utilice la ficha **DemoControlHost** del **Cuadro de herramientas** para agregar instancias del control a `Form1`.  
  
### Para crear una biblioteca de clases de controles  
  
1.  Abra un nuevo proyecto de tipo **Biblioteca de controles de Windows**.  
  
     De forma predeterminada, el proyecto contiene un control compuesto.  
  
2.  Agregue controles y código como se describió en el procedimiento anterior.  
  
3.  Elija un control cuyas clases de herencia no desee que cambien y establezca la propiedad **Modifiers** en **Private**.  
  
4.  Compile el archivo DLL.  
  
### Para heredar de un control compuesto de una biblioteca de clases de controles  
  
1.  En el menú **Archivo**, seleccione **Agregar** y **Nuevo proyecto** para agregar un nuevo proyecto **Aplicación para Windows** a la solución.  
  
2.  En el **Explorador de soluciones**, haga clic con el botón secundario en la carpeta **Referencias** y elija **Agregar referencia** para abrir el cuadro de diálogo **Agregar referencia**.  
  
3.  Seleccione la ficha **Proyectos** y haga doble clic en el proyecto de Biblioteca de controles.  
  
4.  En el menú **Compilar**, haga clic en **Compilar solución**.  
  
5.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el proyecto de Biblioteca de controles y elija **Agregar nuevo elemento** en el menú contextual.  
  
6.  Seleccione la plantilla **Control de usuario heredado** en el cuadro de diálogo **Agregar nuevo elemento**.  
  
7.  En el cuadro de diálogo **Selector de herencia**, haga doble clic en el control del que desea heredar.  
  
     Se agregará un nuevo control al proyecto.  
  
8.  Abra el diseñador visual para el nuevo control y agregue controles constituyentes adicionales.  
  
     Podrá ver los controles constituyentes heredados del control de usuario en la DLL, así como alterar las propiedades de aquellos controles cuya propiedad **Modifiers** sea **Public**.  No podrá cambiar las propiedades del control cuya propiedad **Modifiers** sea **Private**.  
  
## Vea también  
 [Tutorial: Crear un control compuesto con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [Tutorial: Crear un control compuesto con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)   
 [Recomendaciones sobre tipos de controles](../../../../docs/framework/winforms/controls/control-type-recommendations.md)   
 [Cómo: Crear controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)