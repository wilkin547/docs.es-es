---
title: Procedimiento para crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: 9f3350e32c0fbff58678052d26be954d30d512a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301300"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Procedimiento para crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el diseñador
En el siguiente procedimiento, creará una interfaz de usuario de varios paneles similar al usado en Microsoft Outlook, con un **carpeta** lista, un **mensajes** panel y un **devistaprevia** panel. Esta disposición se logra principalmente mediante el acoplamiento de controles con el formulario.  
  
 Al acoplar un control, es necesario determinar cuál de los bordes del contenedor primario de un control está enchufado al. Por lo tanto, si establece la <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Right>, el borde derecho del control estará acoplado al borde derecho de su control principal. Además, el borde del control acoplado cambia para coincidir con el de su control contenedor. Para obtener más información acerca de cómo los <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad, consulte [Cómo: Acoplar controles en Windows Forms](how-to-dock-controls-on-windows-forms.md).  
  
 Este procedimiento se centra en organizar el <xref:System.Windows.Forms.SplitContainer> y los controles del formulario, no en Agregar funcionalidad para que la aplicación que imite a Microsoft Outlook.  
  
 Para crear esta interfaz de usuario, coloque todos los controles dentro de un <xref:System.Windows.Forms.SplitContainer> control, que contiene un <xref:System.Windows.Forms.TreeView> control en el panel izquierdo. El panel derecho de la <xref:System.Windows.Forms.SplitContainer> control contiene un segundo <xref:System.Windows.Forms.SplitContainer> controlar con un <xref:System.Windows.Forms.ListView> control anterior un <xref:System.Windows.Forms.RichTextBox> control. Estos <xref:System.Windows.Forms.SplitContainer> controles permiten el cambio de tamaño independiente de los otros controles del formulario. Puede adaptar las técnicas de este procedimiento para interfaces de usuario personalizadas de elaborar su propio.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Para crear una interfaz de usuario de estilo de Outlook en tiempo de diseño  
  
1. Cree un nuevo proyecto de aplicación de Windows (**archivo** > **New** > **proyecto** > **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).  
  
2. Arrastre un <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas** al formulario. En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
3. Arrastre un <xref:System.Windows.Forms.TreeView> controlar desde la **cuadro de herramientas** hasta el panel izquierdo de la <xref:System.Windows.Forms.SplitContainer> control. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left> haciendo clic en el panel izquierdo, en el editor de valores que se muestra cuando se hace clic en la flecha hacia abajo.  
  
4. Arrastre otro <xref:System.Windows.Forms.SplitContainer> controlar desde la **cuadro de herramientas**; lo coloca en el panel derecho de la <xref:System.Windows.Forms.SplitContainer> control agregado al formulario. En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill> y el <xref:System.Windows.Forms.SplitContainer.Orientation%2A> propiedad <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
5. Arrastre un <xref:System.Windows.Forms.ListView> controlar desde la **cuadro de herramientas** hasta el panel superior de la segunda <xref:System.Windows.Forms.SplitContainer> control agregado al formulario. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.ListView> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
6. Arrastre un <xref:System.Windows.Forms.RichTextBox> controlar desde la **cuadro de herramientas** hasta el panel inferior del segundo <xref:System.Windows.Forms.SplitContainer> control. Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.RichTextBox> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
     En este momento, si presiona F5 para ejecutar la aplicación, el formulario muestra una interfaz de usuario de tres partes, similar de Microsoft Outlook.  
  
    > [!NOTE]
    >  Cuando coloca el puntero del mouse sobre cualquiera de los divisores del <xref:System.Windows.Forms.SplitContainer> controles, puede cambiar el tamaño de las dimensiones internas.  
  
     En este momento en el desarrollo de aplicaciones, ha diseñado una interfaz de usuario sofisticadas. El siguiente paso es continuar con la programación de la propia aplicación, quizás mediante la conexión de la <xref:System.Windows.Forms.TreeView> control y <xref:System.Windows.Forms.ListView> controles a algún tipo de origen de datos. Para obtener más información acerca de cómo conectar los controles a datos, vea [enlace de datos y Windows Forms](../data-binding-and-windows-forms.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer (control)](splitcontainer-control-windows-forms.md)
