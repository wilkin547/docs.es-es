---
title: Procedimiento Heredar de Windows existente controles de formularios
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: dea9b1f870230daff92ac86d00dfda5774309a97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727786"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>Procedimiento Heredar de Windows existente controles de formularios
Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia. Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control. Por ejemplo, si estuviera creando un control que hereda de <xref:System.Windows.Forms.Button>, el nuevo control tendría el aspecto y actúan como exactamente un estándar <xref:System.Windows.Forms.Button> control. A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados. En algunos controles, también puede cambiar la apariencia visual del control heredado reemplazando su <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-inherited-control"></a>Para crear un control heredado  
  
1.  Cree un nuevo proyecto de  **aplicación de Windows Forms**.  
  
2.  En el menú **Proyecto** , elija **Agregar nuevo elemento**.  
  
     Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.  
  
3.  En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.  
  
     Se agrega un nuevo control personalizado al proyecto.  
  
4.  Si usa Visual Basic, en la parte superior del **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**. Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.  
  
5.  Si está utilizando C#, abra CustomControl1.cs en el Editor de código.  
  
6.  Busque la declaración de clase que hereda de <xref:System.Windows.Forms.Control>.  
  
7.  Cambie la clase base para el control a partir del que desee heredar.  
  
     Por ejemplo, si desea heredar <xref:System.Windows.Forms.Button>, cambie la declaración de clase a lo siguiente:  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb. Abra CustomControl1.vb en el Editor de código.  
  
9. Implemente los métodos o propiedades personalizados que vaya a incorporar el control.  
  
10. Si desea modificar la apariencia gráfica del control, invalide el <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
    > [!NOTE]
    >  Reemplazar <xref:System.Windows.Forms.Control.OnPaint%2A> no le permitirá modificar la apariencia de todos los controles. Los controles representados por Windows (por ejemplo, <xref:System.Windows.Forms.TextBox>) nunca llaman a su <xref:System.Windows.Forms.Control.OnPaint%2A> método y, por tanto, nunca usarán el código personalizado. Consulte la documentación de ayuda para el control determinado que desea modificar para ver si el <xref:System.Windows.Forms.Control.OnPaint%2A> método está disponible. Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md). Si no tiene un control <xref:System.Windows.Forms.Control.OnPaint%2A> aparece como un método de miembro, no se puede modificar su apariencia reemplazando este método. Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).  
  
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
  
## <a name="see-also"></a>Vea también
- [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
- [Cómo: Heredar de la clase de Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)
- [Cómo: Heredar de la clase UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)
- [Cómo: Crear controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Tutorial: Heredar de un Control de Windows Forms con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [Tutorial: Heredar de un Control de Windows Forms con VisualC#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
