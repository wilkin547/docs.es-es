---
title: "Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bca5439f247951496d82c03b57ec1fa0e21a8271
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip
El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús. Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.  
  
 Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStripPanel> controles con un formulario MDI. El formulario también admite la combinación de menús con menús secundarios. En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear el menú principal para el formulario. El nombre real del menú varía.  
  
-   Agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas**.  
  
-   Crear un formulario secundario.  
  
-   Organizar <xref:System.Windows.Forms.ToolStripPanel> controles por orden z.  
  
 Cuando haya terminado, tendrá un formulario MDI que admite la combinación de menús y móvil <xref:System.Windows.Forms.ToolStrip> controles.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Los permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] está instalado.  
  
## <a name="creating-the-project"></a>Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### <a name="to-create-the-project"></a>Para crear el proyecto  
  
1.  Cree un proyecto de aplicación de Windows denominado **MDI**.  
  
     Para obtener más información, consulta [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el Diseñador de Windows Forms, seleccione el formulario.  
  
3.  En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.Form.IsMdiContainer%2A> a `true`.  
  
## <a name="creating-the-main-menu"></a>Crear el menú principal  
 El formulario MDI principal contiene el menú principal. El menú principal tiene un elemento de menú denominado **ventana**. Con el **ventana** elemento de menú, puede crear formularios secundarios. Elementos de menú de formularios secundarios se combinan en el menú principal.  
  
#### <a name="to-create-the-main-menu"></a>Para crear el menú principal  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> al formulario.  
  
2.  Agregar un <xref:System.Windows.Forms.ToolStripMenuItem> a la <xref:System.Windows.Forms.MenuStrip> controlar y asígnele el nombre **ventana**.  
  
3.  Seleccione el control <xref:System.Windows.Forms.MenuStrip>.  
  
4.  En la ventana Propiedades, establezca el valor de la <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> propiedad `ToolStripMenuItem1`.  
  
5.  Agregar un subelemento a la **ventana** elemento de menú y, a continuación, el nombre del subelemento **nuevo**.  
  
6.  En la ventana Propiedades, haga clic en **eventos**.  
  
7.  Haga doble clic en el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.  
  
     El Diseñador de Windows Forms genera un controlador de eventos para el <xref:System.Windows.Forms.ToolStripItem.Click> eventos.  
  
8.  Inserte el código siguiente en el controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a>Agregar el Control ToolStripPanel al cuadro de herramientas  
 Cuando usas <xref:System.Windows.Forms.MenuStrip> controles con un formulario MDI que debe tener el <xref:System.Windows.Forms.ToolStripPanel> control. Debe agregar el <xref:System.Windows.Forms.ToolStripPanel> el control a la **cuadro de herramientas** para crear el formulario MDI en el Diseñador de Windows Forms.  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a>Para agregar el control ToolStripPanel al cuadro de herramientas  
  
1.  Abra la **cuadro de herramientas**y, a continuación, haga clic en el **todos los formularios Windows Forms** ficha para mostrar los controles de formularios Windows Forms disponibles.  
  
2.  Haga clic en para abrir el menú contextual y seleccione **elegir elementos**.  
  
3.  En el **elegir elementos del cuadro de herramientas** cuadro de diálogo, desplácese hacia abajo por la **nombre** columna hasta que encuentre **ToolStripPanel**.  
  
4.  Active la casilla de verificación por **ToolStripPanel**y, a continuación, haga clic en **Aceptar**.  
  
     El <xref:System.Windows.Forms.ToolStripPanel> control aparece en el **cuadro de herramientas**.  
  
## <a name="creating-a-child-form"></a>Crear un formulario secundario  
 En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio <xref:System.Windows.Forms.MenuStrip> control. Los elementos de menú para este formulario se combinan con los del formulario primario.  
  
#### <a name="to-define-a-child-form"></a>Para definir un formulario secundario  
  
1.  Agregue un nuevo formulario denominado `ChildForm` al proyecto.  
  
     Para obtener más información, consulte [Cómo: agregar Windows Forms a un proyecto](http://msdn.microsoft.com/en-us/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.MenuStrip> control en el formulario secundario.  
  
3.  Haga clic en el <xref:System.Windows.Forms.MenuStrip> glifo de etiqueta inteligente del control (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) y, a continuación, seleccione **editar elementos**.  
  
4.  En el **Editor de la colección de elementos** diálogo cuadro, agregue un nuevo <xref:System.Windows.Forms.ToolStripMenuItem> denominado **ChildMenuItem** al menú secundario.  
  
     Para obtener más información, consulte [Editor de colección de elementos ToolStrip](http://msdn.microsoft.com/en-us/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## <a name="testing-the-form"></a>Comprobar el formulario  
  
#### <a name="to-test-your-form"></a>Para comprobar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el **ventana** elemento de menú para abrir el menú y, a continuación, haga clic en **nuevo**.  
  
     Se crea un nuevo formulario secundario en el área de cliente del formulario MDI. Menú del formulario secundario se combina con el menú principal.  
  
3.  Cierre el formulario secundario.  
  
     Menú del formulario secundario se quita en el menú principal.  
  
4.  Haga clic en **New** varias veces.  
  
     Los formularios secundarios aparecen automáticamente en el W**ventana** menú elemento porque el <xref:System.Windows.Forms.MenuStrip> del control <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> se asigna la propiedad.  
  
## <a name="adding-toolstrip-support"></a>Agregar compatibilidad de ToolStrip  
 En este procedimiento, agregará cuatro <xref:System.Windows.Forms.ToolStrip> controles al formulario primario MDI. Cada <xref:System.Windows.Forms.ToolStrip> se agrega control dentro de un <xref:System.Windows.Forms.ToolStripPanel> control, que está acoplado al borde del formulario.  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a>Para agregar controles ToolStrip al formulario primario MDI  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStripPanel> al formulario.  
  
2.  Con el <xref:System.Windows.Forms.ToolStripPanel> control seleccionado, haga doble clic en el <xref:System.Windows.Forms.ToolStrip> controlar en el **cuadro de herramientas**.  
  
     A <xref:System.Windows.Forms.ToolStrip> control se crea en el <xref:System.Windows.Forms.ToolStripPanel> control.  
  
3.  Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  En la ventana Propiedades, cambie el valor del control <xref:System.Windows.Forms.Control.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Left>.  
  
     El <xref:System.Windows.Forms.ToolStripPanel> controlar lo acopla en el lado izquierdo del formulario, bajo el menú principal. El área de cliente MDI cambia el tamaño para ajustar el <xref:System.Windows.Forms.ToolStripPanel> control.  
  
5.  Repita los pasos del 1 al 4.  
  
     Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> control a la parte superior del formulario.  
  
     El <xref:System.Windows.Forms.ToolStripPanel> control está acoplado bajo el menú principal, pero a la derecha de la primera <xref:System.Windows.Forms.ToolStripPanel> control. Este paso ilustran la importancia del orden z para colocar correctamente <xref:System.Windows.Forms.ToolStripPanel> controles.  
  
6.  Repita los pasos del 1 al 4 para dos más <xref:System.Windows.Forms.ToolStripPanel> controles.  
  
     Acoplar el nuevo <xref:System.Windows.Forms.ToolStripPanel> controles a la derecha e inferior del formulario.  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a>Organizar los controles ToolStripPanel por orden Z  
 La posición de un acoplada <xref:System.Windows.Forms.ToolStripPanel> control en el formulario MDI viene determinado por la posición del control en el orden z. Puede organizar con facilidad el orden z de los controles en la ventana Esquema del documento.  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a>Para organizar los controles ToolStripPanel por orden Z  
  
1.  En el **vista** menú, haga clic en **otras ventanas**y, a continuación, haga clic en **esquema del documento**.  
  
     La organización de su <xref:System.Windows.Forms.ToolStripPanel> controles desde el procedimiento anterior no es estándar. Esto es porque el orden z no es correcto. Utilice la ventana Esquema del documento para cambiar el orden z de los controles.  
  
2.  En la ventana Esquema del documento, seleccione **ToolStripPanel4**.  
  
3.  Haga clic en el botón de flecha abajo y otra vez, hasta que **ToolStripPanel4** en la parte inferior de la lista.  
  
     El **ToolStripPanel4** control está acoplado a la parte inferior del formulario, debajo de los demás controles.  
  
4.  Seleccione **ToolStripPanel2**.  
  
5.  Haga clic una vez en el botón de flecha abajo para colocar el control en tercer lugar en la lista.  
  
     El **ToolStripPanel2** control está acoplado a la parte superior del formulario, bajo el menú principal y encima de los otros controles.  
  
6.  Seleccione los distintos controles en el **esquema del documento** ventana y moverlos a distintas posiciones en el orden z. Tenga en cuenta el efecto del orden z en la posición de los controles acoplados. Utilice CTRL-Z o **deshacer** en el **editar** menú para deshacer los cambios.  
  
## <a name="checkpoint"></a>Punto de control  
  
#### <a name="to-test-your-form"></a>Para comprobar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el control de un <xref:System.Windows.Forms.ToolStrip> controlar y arrastrar el control a otras posiciones en el formulario.  
  
     Puede arrastrar una <xref:System.Windows.Forms.ToolStrip> control de una <xref:System.Windows.Forms.ToolStripPanel> control a otro.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial, ha creado un formulario MDI principal con <xref:System.Windows.Forms.ToolStrip> controles y combinación de menús. Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:  
  
-   Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, consulte [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Crea un formulario con un menú estándar rellenado automáticamente. Para obtener más información, consulte [Tutorial: proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Asigne el <xref:System.Windows.Forms.ToolStrip> controla un aspecto profesional. Para obtener más información, consulte [Cómo: establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [Insertar un elemento MenuStrip en un menú desplegable MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
