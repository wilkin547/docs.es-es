---
title: "C&#243;mo: Explorar datos con el control BindingNavigator de formularios Windows Forms | Microsoft Docs"
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
  - "BindingNavigator (control) [Windows Forms], desplazarse por datos"
  - "datos [Windows Forms], navegar"
  - "exploración de datos"
  - "ejemplos [Windows Forms], BindingNavigator (control)"
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Explorar datos con el control BindingNavigator de formularios Windows Forms
La incorporación del control <xref:System.Windows.Forms.BindingNavigator> de Windows Forms permite a los desarrolladores proporcionar a los usuarios finales una sencilla interfaz de usuario de navegación y manipulación de datos en los formularios que creen.  
  
 El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> con botones preconfigurados para navegar al registro primero, último, anterior y siguiente en un conjunto de datos, así como botones para agregar y eliminar registros.  Agregar botones al control <xref:System.Windows.Forms.BindingNavigator> es fácil porque es un control <xref:System.Windows.Forms.ToolStrip>.  Consulte también [Cómo: Agregar los botones Cargar, Guardar y Cancelar al control BindingNavigator de Windows Forms](http://msdn.microsoft.com/library/safa4957%20\(v=vs.110\)).  
  
 Por cada botón del control <xref:System.Windows.Forms.BindingNavigator> hay un miembro correspondiente del componente <xref:System.Windows.Forms.BindingSource> que permite la misma funcionalidad mediante programación.  Por ejemplo, el botón <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, el botón <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>, y así sucesivamente.  Como resultado, habilitar el control <xref:System.Windows.Forms.BindingNavigator> para navegar por los registros de datos es tan sencillo como establecer la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> en el componente <xref:System.Windows.Forms.BindingSource> correspondiente en el formulario.  
  
### Para configurar el control BindingNavigator  
  
1.  Agregue un componente <xref:System.Windows.Forms.BindingSource> llamado `bindingSource1` y dos controles <xref:System.Windows.Forms.TextBox> llamados `textBox1` y `textBox2`.  
  
2.  Enlace `bindingSource1`  a los datos y los controles de cuadro de texto a `bindingSource1`.  Para ello, pegue el siguiente código en el formulario y llame a `LoadData` desde el constructor del formulario o al método de control de eventos <xref:System.Windows.Forms.Form.Load>.  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3.  Agregue un control <xref:System.Windows.Forms.BindingNavigator> llamado `bindingNavigator1` al formulario.  
  
4.  Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> de `bindingNavigator1` en `bindingSource1`.  Puede hacerlo con el diseñador o en el código.  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## Ejemplo  
 El ejemplo de código siguiente es el ejemplo completo de los pasos enumerados anteriormente.  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingNavigator>   
 [BindingNavigator \(Control\)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)