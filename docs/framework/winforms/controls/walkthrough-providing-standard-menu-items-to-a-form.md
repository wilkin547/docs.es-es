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
ms.openlocfilehash: c0e3a9471afd05ec0e07e8d8a71ffd76c91ec14d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Tutorial: Proporcionar elementos de menú estándar a un formulario
Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.  
  
 Este tutorial muestra cómo utilizar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar. El formulario también responde cuando un usuario selecciona un elemento de menú. En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear un menú estándar.  
  
-   Crear un <xref:System.Windows.Forms.StatusStrip> control.  
  
-   Control de selección de elementos de menú.  
  
 Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Crear un proyecto de aplicación de Windows denominado **StandardMenuForm**.  
  
     Para más información, consulte [Cómo: Crear un proyecto de aplicación para Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el Diseñador de Windows Forms, seleccione el formulario.  
  
## <a name="creating-a-standard-menu"></a>Crear un menú estándar  
 El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.  
  
#### <a name="to-create-a-standard-menu"></a>Para crear un menú estándar  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.  
  
     El <xref:System.Windows.Forms.MenuStrip> se rellena con los elementos de menú estándar.  
  
3.  Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.  
  
## <a name="creating-a-statusstrip-control"></a>Crear un Control StatusStrip  
 Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms. En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.  
  
#### <a name="to-create-a-statusstrip-control"></a>Para crear un control StatusStrip  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.  
  
     El <xref:System.Windows.Forms.StatusStrip> control automáticamente se acopla a la parte inferior del formulario.  
  
2.  Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar una <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.  
  
## <a name="handling-item-selection"></a>Selección de elementos de control  
 Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> evento para responder cuando el usuario selecciona un elemento de menú.  
  
#### <a name="to-handle-item-selection"></a>Para controlar la selección de elementos  
  
1.  Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.  
  
2.  En el **propiedades** ventana, haga clic en **eventos**.  
  
3.  Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.  
  
     El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.  
  
4.  Inserte el código siguiente en el controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Insertar el `UpdateStatus` definición de método de utilidad en el formulario.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a>Punto de control  
  
#### <a name="to-test-your-form"></a>Para comprobar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el **archivo** elemento de menú para abrir el menú.  
  
3.  En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.  
  
     El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial, ha creado un formulario con un menú estándar. Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:  
  
-   Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles. Para obtener más información, consulte [Tutorial: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Asigne el <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional. Para obtener más información, consulte [Cómo: establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
