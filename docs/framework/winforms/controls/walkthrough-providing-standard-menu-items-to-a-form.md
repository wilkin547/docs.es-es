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
ms.openlocfilehash: ebfacadfee3ea069359a72ea0402751e9e6280d7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211507"
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a>Tutorial: Proporcionar elementos de menú estándar a un formulario

Puede proporcionar un menú estándar para los formularios con el control <xref:System.Windows.Forms.MenuStrip>.

Este tutorial muestra cómo usar un <xref:System.Windows.Forms.MenuStrip> control para crear un menú estándar. El formulario también responde cuando un usuario selecciona un elemento de menú. En este tutorial se muestran las tareas siguientes:

- Crear un proyecto de Windows Forms.

- Crear un menú estándar.

- Creación de un <xref:System.Windows.Forms.StatusStrip> control.

- Control de selección de elementos de menú.

Cuando haya terminado, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un <xref:System.Windows.Forms.StatusStrip> control.

Para copiar el código de este tema como una sola lista, vea [Cómo: Proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md).

## <a name="prerequisites"></a>Requisitos previos

Necesitará Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Crear el proyecto

1. En Visual Studio, cree un proyecto de aplicación de Windows denominado **StandardMenuForm** (**archivo** > **New** > **proyecto**   >  **Visual C#**  o **Visual Basic** > **escritorio clásico de**  >  **Aplicación de Windows Forms**).

2. En el Diseñador de formularios de Windows, seleccione el formulario.

## <a name="create-a-standard-menu"></a>Crear un menú estándar

El Diseñador de Windows Forms puede rellenar automáticamente un <xref:System.Windows.Forms.MenuStrip> control con elementos de menú estándar.

1. Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control al formulario.

2. Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y seleccione **insertar elementos estándar**.

     El <xref:System.Windows.Forms.MenuStrip> control se rellena con los elementos de menú estándar.

3. Haga clic en el **archivo** elemento de menú para ver sus elementos de menú predeterminados y los iconos correspondientes.

## <a name="create-a-statusstrip-control"></a>Crear un control StatusStrip

Use el <xref:System.Windows.Forms.StatusStrip> control para mostrar el estado de las aplicaciones de Windows Forms. En el ejemplo actual, se muestran los elementos de menú seleccionados por el usuario en un <xref:System.Windows.Forms.StatusStrip> control.

1. Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.StatusStrip> control al formulario.

     El <xref:System.Windows.Forms.StatusStrip> control se acopla automáticamente a la parte inferior del formulario.

2. Haga clic en el <xref:System.Windows.Forms.StatusStrip> del control de botón de lista desplegable y seleccione **StatusLabel como** para agregar un <xref:System.Windows.Forms.ToolStripStatusLabel> el control a la <xref:System.Windows.Forms.StatusStrip> control.

## <a name="handle-item-selection"></a>Controlar la selección de elementos

Controlar la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos para responder cuando el usuario selecciona un elemento de menú.

1. Haga clic en el **archivo** elemento de menú que creó en la creación una sección de menú estándar.

2. En la ventana **Propiedades**, haga clic en **Eventos**.

3. Haga doble clic en el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.

     El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> eventos.

4. Inserte el código siguiente en el controlador de eventos.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]

5. Insertar el `UpdateStatus` definición de método de utilidad en el formulario.

     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]

## <a name="checkpoint--test-your-form"></a>Punto de comprobación: probar el formulario

1. Presione **F5** para compilar y ejecutar el formulario.

2. Haga clic en el **archivo** elemento de menú para abrir el menú.

3. En el **archivo** menú, haga clic en uno de los elementos para seleccionarlo.

     El <xref:System.Windows.Forms.StatusStrip> control muestra el elemento seleccionado.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado un formulario con un menú estándar. Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:

- Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).

- Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles. Para obtener más información, vea [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

- Asigne a su <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional. Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Control MenuStrip](menustrip-control-windows-forms.md)
