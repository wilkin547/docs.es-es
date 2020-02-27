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
ms.openlocfilehash: ee80aad445c00bb4b98b49c80495fa512150bcef
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628779"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Tutorial: Proporcionar elementos de menú estándar a un formulario

Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.

En este tutorial se muestra cómo utilizar un control de <xref:System.Windows.Forms.MenuStrip> para crear un menú estándar. El formulario también responde cuando un usuario selecciona un elemento de menú. En este tutorial se muestran las siguientes tareas:

- Crear un proyecto de Windows Forms.

- Crear un menú estándar.

- Crear un control de <xref:System.Windows.Forms.StatusStrip>.

- Control de la selección de elementos de menú.

Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un control de <xref:System.Windows.Forms.StatusStrip>.

Para copiar el código de este tema como una sola lista, vea [Cómo: proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md).

## <a name="prerequisites"></a>Prerequisites

Necesitará Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Creación del proyecto

1. En Visual Studio, cree un proyecto de aplicación para Windows denominado **StandardMenuForm** (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación**de **escritorio clásico** > Windows Forms.

2. En el Diseñador de Windows Forms, seleccione el formulario.

## <a name="create-a-standard-menu"></a>Crear un menú estándar

El Diseñador de Windows Forms puede rellenar automáticamente un control <xref:System.Windows.Forms.MenuStrip> con elementos de menú estándar.

1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.

2. Haga clic en el glifo de acciones del diseñador del <xref:System.Windows.Forms.MenuStrip> del control (![flecha negra pequeña](./media/designer-actions-glyph.gif)) y seleccione **insertar elementos estándar**.

     El control <xref:System.Windows.Forms.MenuStrip> se rellena con los elementos de menú estándar.

3. Haga clic en el elemento de menú **archivo** para ver sus elementos de menú predeterminados y sus iconos correspondientes.

## <a name="create-a-statusstrip-control"></a>Crear un control StatusStrip

Use el control <xref:System.Windows.Forms.StatusStrip> para mostrar el estado de las aplicaciones de Windows Forms. En el ejemplo actual, los elementos de menú seleccionados por el usuario se muestran en un control de <xref:System.Windows.Forms.StatusStrip>.

1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.StatusStrip> al formulario.

     El control <xref:System.Windows.Forms.StatusStrip> se acopla automáticamente a la parte inferior del formulario.

2. Haga clic en el botón desplegable del control de <xref:System.Windows.Forms.StatusStrip> y seleccione **StatusLabel** para agregar un control de <xref:System.Windows.Forms.ToolStripStatusLabel> al control de <xref:System.Windows.Forms.StatusStrip>.

## <a name="handle-item-selection"></a>Controlar la selección de elementos

Controle el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> para responder cuando el usuario selecciona un elemento de menú.

1. Haga clic en el elemento de menú **archivo** que creó en la sección crear un menú estándar.

2. En la ventana **Propiedades**, haga clic en **Eventos**.

3. Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.

     El Diseñador de Windows Forms genera un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.

4. Inserte el código siguiente en el controlador de eventos.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. Inserte el `UpdateStatus` definición del método de utilidad en el formulario.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>Punto de control: prueba del formulario

1. Presione **F5** para compilar y ejecutar el formulario.

2. Haga clic en el elemento de menú **archivo** para abrir el menú.

3. En el menú **archivo** , haga clic en uno de los elementos para seleccionarlo.

     El control <xref:System.Windows.Forms.StatusStrip> muestra el elemento seleccionado.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado un formulario con un menú estándar. Puede usar la familia de controles de <xref:System.Windows.Forms.ToolStrip> para muchos otros propósitos:

- Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, vea [información general sobre el componente ContextMenu](contextmenu-component-overview-windows-forms.md).

- Cree un formulario de interfaz de múltiples documentos (MDI) con controles de acoplamiento <xref:System.Windows.Forms.ToolStrip>. Para obtener más información, vea [Tutorial: crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

- Dé a los <xref:System.Windows.Forms.ToolStrip> controles un aspecto profesional. Para obtener más información, vea [Cómo: establecer el representador de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [MenuStrip (control)](menustrip-control-windows-forms.md)
