---
title: 'Tutorial: Proporcionar elementos de menú estándar a un formulario'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
ms.openlocfilehash: b0f88f8c28b613b9eae580c851ee4dd1282e77e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505112"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Tutorial: Proporcionar elementos de menú estándar a un formulario
Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.  
  
 Este tutorial muestra cómo usar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar. El formulario también responde cuando un usuario selecciona un elemento de menú. En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de Windows Forms.  
  
-   Crear un menú estándar.  
  
-   Creación de un <xref:System.Windows.Forms.StatusStrip> control.  
  
-   Control de selección de elementos de menú.  
  
 Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación de Windows denominado **StandardMenuForm** (**archivo** > **New** > **proyecto**  >  **Visual C#** o **Visual Basic** > **escritorio clásico de** > **Windows Forms Aplicación**).  
  
2.  En el Diseñador de formularios de Windows, seleccione el formulario.  
  
## <a name="creating-a-standard-menu"></a>Crear un menú estándar  
 El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.  
  
#### <a name="to-create-a-standard-menu"></a>Para crear un menú estándar  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.  
  
     El <xref:System.Windows.Forms.MenuStrip> control se rellena con los elementos de menú estándar.  
  
3.  Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.  
  
## <a name="creating-a-statusstrip-control"></a>Crear un Control StatusStrip  
 Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms. En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.  
  
#### <a name="to-create-a-statusstrip-control"></a>Para crear un control StatusStrip  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.  
  
     El <xref:System.Windows.Forms.StatusStrip> control se acopla automáticamente a la parte inferior del formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar un <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.  
  
## <a name="handling-item-selection"></a>Selección de elementos de control  
 Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos para responder cuando el usuario selecciona un elemento de menú.  
  
#### <a name="to-handle-item-selection"></a>Para controlar la selección de elementos  
  
1.  Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.  
  
2.  En la ventana **Propiedades**, haga clic en **Eventos**.  
  
3.  Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.  
  
     El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.  
  
4.  Inserte el código siguiente en el controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Insertar el `UpdateStatus` definición de método de utilidad en el formulario.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Punto de control  
  
#### <a name="to-test-your-form"></a>Para probar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el **archivo** elemento de menú para abrir el menú.  
  
3.  En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.  
  
     El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial, ha creado un formulario con un menú estándar. Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:  
  
-   Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles. Para obtener más información, vea [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional. Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
