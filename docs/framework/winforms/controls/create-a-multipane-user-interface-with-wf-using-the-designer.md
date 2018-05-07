---
title: 'Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: d0faf86ce31dad6bc053b5af8902e500d2b1c75b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Diseñador
En el siguiente procedimiento, creará una interfaz de usuario de varios paneles que es similar al utilizado en Microsoft Outlook, con un **carpeta** lista, un **mensajes** panel y un **devistaprevia** panel. Esta disposición se consigue principalmente mediante el acoplamiento de controles con el formulario.  
  
 Al acoplar un control, se determina cuál de los bordes del contenedor primario de un control está enchufado al. Por lo tanto, si establece la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Right>, el borde derecho del control se acoplará al borde derecho de su control primario. Además, el borde del control acoplado cambia para coincidir con el de su control contenedor. Para obtener más información acerca de cómo los <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad, consulte [Cómo: acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Este procedimiento se centra en organizar el <xref:System.Windows.Forms.SplitContainer> y los demás controles en el formulario, no en Agregar funcionalidad para hacer que la aplicación se comporten como Microsoft Outlook.  
  
 Para crear esta interfaz de usuario, coloque todos los controles dentro de un <xref:System.Windows.Forms.SplitContainer> control, que contiene un <xref:System.Windows.Forms.TreeView> control en el panel izquierdo. El panel derecho de la <xref:System.Windows.Forms.SplitContainer> control contiene un segundo <xref:System.Windows.Forms.SplitContainer> controlar con un <xref:System.Windows.Forms.ListView> control anterior un <xref:System.Windows.Forms.RichTextBox> control. Estos <xref:System.Windows.Forms.SplitContainer> controles permiten el cambio de tamaño independientemente de los demás controles en el formulario. Puede adaptar las técnicas de este procedimiento para interfaces de usuario personalizadas de elaborar de su elección.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Para crear una interfaz de usuario de estilo Outlook en tiempo de diseño  
  
1.  Crear un nuevo proyecto de aplicación de Windows. Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Arrastre un <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas** al formulario. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3.  Arrastre un <xref:System.Windows.Forms.TreeView> controlar desde la **cuadro de herramientas** hasta el panel izquierdo de la <xref:System.Windows.Forms.SplitContainer> control. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left> haciendo clic en el panel izquierdo, en el editor de valores que se muestra cuando se hace clic en la flecha hacia abajo.  
  
4.  Arrastre otra <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas**; lo coloca en el panel derecho de la <xref:System.Windows.Forms.SplitContainer> control agregado al formulario. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill> y <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad a <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5.  Arrastre un <xref:System.Windows.Forms.ListView> controlar desde la **cuadro de herramientas** hasta el panel superior del segundo <xref:System.Windows.Forms.SplitContainer> control agregado al formulario. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.ListView> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
6.  Arrastre un <xref:System.Windows.Forms.RichTextBox> controlar desde la **cuadro de herramientas** hasta el panel inferior del segundo <xref:System.Windows.Forms.SplitContainer> control. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.RichTextBox> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     En este punto, si presiona F5 para ejecutar la aplicación, el formulario muestra una interfaz de usuario de tres partes, similar de Microsoft Outlook.  
  
    > [!NOTE]
    >  Cuando coloca el puntero del mouse sobre cualquiera de los divisores de los <xref:System.Windows.Forms.SplitContainer> controles, puede cambiar el tamaño de las dimensiones internas.  
  
     En este momento en el desarrollo de aplicaciones, se ha diseñado una interfaz de usuario sofisticada. El siguiente paso es continuar con la programación de la propia aplicación, quizás mediante la conexión de la <xref:System.Windows.Forms.TreeView> control y <xref:System.Windows.Forms.ListView> controles a algún tipo de origen de datos. Para obtener más información acerca de cómo conectar controles a datos, vea [enlace de datos y formularios Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer (control)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
