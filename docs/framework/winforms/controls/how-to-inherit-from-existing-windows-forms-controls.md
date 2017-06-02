---
title: "C&#243;mo: Heredar de controles de formularios Windows Forms existentes | Microsoft Docs"
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
  - "herencia, controles personalizados de Windows Forms"
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Heredar de controles de formularios Windows Forms existentes
Si desea extender la funcionalidad de un control existente, puede crear un control derivado de un control existente por medio de la herencia.  Cuando herede de un control existente, heredará toda la funcionalidad y las propiedades visuales del control.  Por ejemplo, si estuviera creando un control que heredara de <xref:System.Windows.Forms.Button>, el nuevo control tendría la misma apariencia y funcionaría exactamente igual que un control <xref:System.Windows.Forms.Button> estándar.  A continuación, podría extender o modificar la funcionalidad del nuevo control por medio de la implementación de métodos y propiedades personalizados.  En algunos controles, puede cambiar también la apariencia visual del control heredado reemplazando su método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un control heredado  
  
1.  Cree un nuevo proyecto **Aplicación de Windows Forms**.  
  
2.  En el menú **Proyecto**, elija **Agregar nuevo elemento**.  
  
     Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.  
  
3.  En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.  
  
     Se agregará un nuevo control personalizado al proyecto.  
  
4.  Si usa Visual Basic, en la parte superior del **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**.  Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.  
  
5.  Si usa C\#, abra CustomControl1.cs en el Editor de código.  
  
6.  Busque la declaración de clase, que hereda de <xref:System.Windows.Forms.Control>.  
  
7.  Cambie la clase base al control del que desea heredar.  
  
     Por ejemplo, si desea heredar de <xref:System.Windows.Forms.Button>, cambie la declaración de clase por lo siguiente:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Si usa Visual Basic, guarde y cierre CustomControl1.Designer.vb.  Abra CustomControl1.vb en el Editor de código.  
  
9. Implemente los métodos o propiedades personalizados que vaya a incorporar el control.  
  
10. Si desea modificar la apariencia gráfica del control, reemplace el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
    > [!NOTE]
    >  El hecho de reemplazar <xref:System.Windows.Forms.Control.OnPaint%2A> no le permitirá modificar la apariencia de todos los controles.  Los controles representados por Windows \(por ejemplo <xref:System.Windows.Forms.TextBox>\) nunca llaman a su método <xref:System.Windows.Forms.Control.OnPaint%2A> y, por tanto, no utilizan nunca el código personalizado.  Consulte la documentación de Ayuda del control específico que desee modificar para comprobar si el método <xref:System.Windows.Forms.Control.OnPaint%2A> está disponible.  Para obtener una lista de todos los controles de Windows Forms, vea [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).  Si un control no dispone del método <xref:System.Windows.Forms.Control.OnPaint%2A> como método miembro, no podrá modificar su apariencia reemplazando este método.  Para obtener más información acerca de la representación personalizada, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. Guarde y pruebe el control.  
  
## Vea también  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)   
 [Cómo: Heredar de una clase de control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)   
 [Cómo: Heredar de una clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)   
 [Cómo: Crear controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)   
 [Solucionar problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)   
 [Tutorial: Heredar de un control de formularios Windows Forms con Visual C\#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)