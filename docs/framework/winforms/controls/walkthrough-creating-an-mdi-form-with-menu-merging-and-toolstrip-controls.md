---
title: 'Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
ms.openlocfilehash: e0343b98cb71521b35418e70550a93e0bfe20fa8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628792"
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip

El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús. Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.

En este tutorial se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI. El formulario también admite la combinación de menús con menús secundarios. En este tutorial se muestran las siguientes tareas:

- Crear un proyecto de Windows Forms.

- Crear el menú principal del formulario. El nombre real del menú variará.

- Agregar el control <xref:System.Windows.Forms.ToolStripPanel> al **cuadro de herramientas**.

- Crear un formulario secundario.

- Organizar los controles de <xref:System.Windows.Forms.ToolStripPanel> por orden z.

Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y los controles de <xref:System.Windows.Forms.ToolStrip> móviles.

Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).

## <a name="prerequisites"></a>Prerequisites

Necesitará Visual Studio para completar este tutorial.

## <a name="create-the-project"></a>Creación del proyecto

1. En Visual Studio, cree un proyecto de aplicación para Windows denominado **MdiForm** (**archivo** > **nuevo** **proyecto** de >  > **Visual C#**  o **Visual Basic** > **aplicación**de **escritorio clásico** > Windows Forms.

2. En el Diseñador de Windows Forms, seleccione el formulario.

3. En el ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.

## <a name="create-the-main-menu"></a>Crear el menú principal

El formulario MDI primario contiene el menú principal. El menú principal tiene un elemento de menú denominado **Window**. Con el elemento de menú **ventana** , puede crear formularios secundarios. Los elementos de menú de los formularios secundarios se combinan en el menú principal.

1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.

2. Agregue un <xref:System.Windows.Forms.ToolStripMenuItem> al control <xref:System.Windows.Forms.MenuStrip> y asígnele el nombre **Window**.

3. Seleccione el control <xref:System.Windows.Forms.MenuStrip>.

4. En el ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> en `ToolStripMenuItem1`.

5. Agregue un subelemento al elemento de menú **ventana** y, a continuación, asigne el nombre **New**al subelemento.

6. En el ventana Propiedades, haga clic en **eventos**.

7. Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripItem.Click>.

     El Diseñador de Windows Forms genera un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click>.

8. Inserte el código siguiente en el controlador de eventos.

     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]

## <a name="add-the-toolstrippanel-control-to-the-toolbox"></a>Agregar el control ToolStripPanel al cuadro de herramientas

Cuando use <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI, debe tener el control <xref:System.Windows.Forms.ToolStripPanel>. Debe agregar el control <xref:System.Windows.Forms.ToolStripPanel> al cuadro de **herramientas** para compilar el formulario MDI en el diseñador de Windows Forms.

1. Abra el **cuadro de herramientas**y, a continuación, haga clic en la pestaña **todos los Windows Forms** para mostrar los controles de Windows Forms disponibles.

2. Haga clic con el botón derecho para abrir el menú contextual y seleccione **elegir elementos**.

3. En el cuadro de diálogo **elegir elementos del cuadro de herramientas** , desplácese hacia abajo en la columna **nombre** hasta que encuentre **ToolStripPanel**.

4. Active la casilla de **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.

     El control <xref:System.Windows.Forms.ToolStripPanel> aparece en el **cuadro de herramientas**.

## <a name="create-a-child-form"></a>Crear un formulario secundario

En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio control <xref:System.Windows.Forms.MenuStrip>. Los elementos de menú para este formulario se combinan con los del formulario primario.

1. Agregue un nuevo formulario denominado `ChildForm` al proyecto.

     Para obtener más información, vea [Cómo: agregar Windows Forms a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y2xxdce3(v=vs.100)).

2. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario secundario.

3. Haga clic en el glifo de acciones del diseñador del <xref:System.Windows.Forms.MenuStrip> del control (![flecha negra pequeña](./media/designer-actions-glyph.gif)) y, a continuación, seleccione **Editar elementos**.

4. En el cuadro de diálogo Editor de la **colección de elementos** , agregue una nueva <xref:System.Windows.Forms.ToolStripMenuItem> denominada **ChildMenuItem** al menú secundario.

     Para obtener más información, vea [Editor de colecciones de elementos ToolStrip](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233643(v=vs.100)).

## <a name="test-the-form"></a>Prueba del formulario

1. Presione **F5** para compilar y ejecutar el formulario.

2. Haga clic en el elemento de menú **ventana** para abrir el menú y, a continuación, haga clic en **nuevo**.

     Se crea un nuevo formulario secundario en el área cliente MDI del formulario. El menú del formulario secundario se combina con el menú principal.

3. Cierre el formulario secundario.

     El menú del formulario secundario se quita del menú principal.

4. Haga clic en **nuevo** varias veces.

     Los formularios secundarios aparecen automáticamente en el elemento de menú **ventana** porque se asigna la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> del control <xref:System.Windows.Forms.MenuStrip>.

## <a name="add-toolstrip-support"></a>Agregar compatibilidad con ToolStrip

En este procedimiento, agregará cuatro controles <xref:System.Windows.Forms.ToolStrip> al formulario MDI primario. Cada control de <xref:System.Windows.Forms.ToolStrip> se agrega dentro de un control <xref:System.Windows.Forms.ToolStripPanel>, que está acoplado al borde del formulario.

1. En el **cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ToolStripPanel> al formulario.

2. Con el control <xref:System.Windows.Forms.ToolStripPanel> seleccionado, haga doble clic en el control <xref:System.Windows.Forms.ToolStrip> en el **cuadro de herramientas**.

     Se crea un control <xref:System.Windows.Forms.ToolStrip> en el control <xref:System.Windows.Forms.ToolStripPanel>.

3. Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.

4. En el ventana Propiedades, cambie el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control por <xref:System.Windows.Forms.DockStyle.Left>.

     El control <xref:System.Windows.Forms.ToolStripPanel> acopla en el lado izquierdo del formulario, debajo del menú principal. El área del cliente MDI cambia de tamaño para ajustarse al control <xref:System.Windows.Forms.ToolStripPanel>.

5. Repita los pasos del 1 al 4.

     Acople el nuevo control <xref:System.Windows.Forms.ToolStripPanel> en la parte superior del formulario.

     El control <xref:System.Windows.Forms.ToolStripPanel> se acopla debajo del menú principal, pero a la derecha del primer control <xref:System.Windows.Forms.ToolStripPanel>. Este paso muestra la importancia del orden z en el posicionamiento correcto de los controles <xref:System.Windows.Forms.ToolStripPanel>.

6. Repita los pasos del 1 al 4 para dos controles más <xref:System.Windows.Forms.ToolStripPanel>.

     Acople los nuevos controles de <xref:System.Windows.Forms.ToolStripPanel> a la parte derecha e inferior del formulario.

## <a name="arrange-toolstrippanel-controls-by-z-order"></a>Organizar los controles ToolStripPanel por orden Z

La posición de un control de <xref:System.Windows.Forms.ToolStripPanel> acoplado en el formulario MDI viene determinada por la posición del control en el orden z. Puede organizar fácilmente el orden z de los controles en la ventana esquema del documento.

1. En el menú **Ver** , haga clic en **otras ventanas**y, a continuación, haga clic en **esquema del documento**.

     La organización de los controles de <xref:System.Windows.Forms.ToolStripPanel> del procedimiento anterior no es estándar. Esto se debe a que el orden z no es correcto. Use la ventana esquema del documento para cambiar el orden z de los controles.

2. En la ventana esquema del documento, seleccione **ToolStripPanel4**.

3. Haga clic repetidamente en el botón de flecha abajo, hasta que **ToolStripPanel4** esté en la parte inferior de la lista.

     El control **ToolStripPanel4** se acopla a la parte inferior del formulario, debajo de los demás controles.

4. Seleccione **ToolStripPanel2**.

5. Haga clic en el botón de flecha abajo una vez para colocar el control en tercer lugar en la lista.

     El control **ToolStripPanel2** se acopla a la parte superior del formulario, debajo del menú principal y encima de los demás controles.

6. Seleccione varios controles en la ventana **esquema del documento** y muévalos a posiciones diferentes en el orden z. Observe el efecto del orden z en la posición de los controles acoplados. Use CTRL-Z o **Deshacer** en el menú **edición** para deshacer los cambios.

## <a name="checkpoint---test-your-form"></a>Punto de control: prueba del formulario

1. Presione **F5** para compilar y ejecutar el formulario.

2. Haga clic en el control de un control de <xref:System.Windows.Forms.ToolStrip> y arrastre el control a distintas posiciones del formulario.

     Puede arrastrar un control de <xref:System.Windows.Forms.ToolStrip> de un control <xref:System.Windows.Forms.ToolStripPanel> a otro.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado un formulario MDI primario con <xref:System.Windows.Forms.ToolStrip> controles y la combinación de menús. Puede usar la familia de controles de <xref:System.Windows.Forms.ToolStrip> para muchos otros propósitos:

- Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, vea [información general sobre el componente ContextMenu](contextmenu-component-overview-windows-forms.md).

- Ha creado un formulario con un menú estándar rellenado automáticamente. Para obtener más información, vea [Tutorial: proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).

- Dé a los <xref:System.Windows.Forms.ToolStrip> controles un aspecto profesional. Para obtener más información, vea [Cómo: establecer el representador de ToolStrip para una aplicación](how-to-set-the-toolstrip-renderer-for-an-application.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Crear formularios principales MDI](../advanced/how-to-create-mdi-parent-forms.md)
- [Crear formularios MDI secundarios](../advanced/how-to-create-mdi-child-forms.md)
- [Insertar un elemento MenuStrip en un menú desplegable MDI](how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)
- [ToolStrip (control)](toolstrip-control-windows-forms.md)
