---
title: 'Tutorial: Crear un control ToolStrip de estilo profesional'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 22ec7b85973d606d329fe1c58f8cef7036fc1a8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115796"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a>Tutorial: Crear un control ToolStrip de estilo profesional
Puedes usar la aplicación <xref:System.Windows.Forms.ToolStrip> controla un aspecto y comportamiento profesional escribiendo su propia clase derivada de la <xref:System.Windows.Forms.ToolStripProfessionalRenderer> tipo.  
  
 Este tutorial muestra cómo usar <xref:System.Windows.Forms.ToolStrip> controles para crear un control compuesto que es similar a la **panel de navegación** proporcionado por Microsoft® Outlook®. En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de biblioteca de controles de Windows.  
  
-   Diseñar el Control StackView.  
  
-   Implementación de un representador personalizado.  
  
 Cuando haya terminado, tendrá un control de cliente personalizado reutilizable con la apariencia de un control de Microsoft Office XP professional.  
  
 Para copiar el código de este tema como una sola lista, vea [Cómo: Crear un Control ToolStrip de estilo profesional](how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde está instalado Visual Studio.  
  
## <a name="creating-a-windows-control-library-project"></a>Crear un proyecto de biblioteca de controles de Windows  
 El primer paso es crear el proyecto de biblioteca de controles.  
  
#### <a name="to-create-the-control-library-project"></a>Para crear el proyecto de biblioteca de control  
  
1.  Crear un nuevo proyecto de biblioteca de controles de Windows denominado `StackViewLibrary`.  
  
2.  En **el Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de origen denominado "UserControl1.cs" o "UserControl1.vb", dependiendo del lenguaje que prefiera.  
  
     Para obtener más información, vea [Cómo: Quitar, eliminar y excluir elementos](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).  
  
3.  Agregue un nuevo <xref:System.Windows.Forms.UserControl> elemento a la **StackViewLibrary** proyecto. Dé el nuevo archivo de origen en un nombre de base de `StackView`.  
  
## <a name="designing-the-stackview-control"></a>Diseñar el Control StackView  
 El `StackView` control es un control compuesto con un elemento secundario <xref:System.Windows.Forms.ToolStrip> control. Para obtener más información acerca de los controles compuestos, vea [variedades de controles personalizados](varieties-of-custom-controls.md).  
  
#### <a name="to-design-the-stackview-control"></a>Para diseñar el control StackView  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.ToolStrip> control a la superficie de diseño.  
  
2.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStrip> propiedades del control según la tabla siguiente.  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |Name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Acoplar|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |Fuente|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |Relleno|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  En el Diseñador de formularios de Windows, haga clic en el <xref:System.Windows.Forms.ToolStrip> del control **agregar** botón y agregue un <xref:System.Windows.Forms.ToolStripButton> a la `stackStrip` control.  
  
4.  En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.ToolStripButton> propiedades del control según la tabla siguiente.  
  
    |Propiedad|Valor|  
    |--------------|-----------|  
    |Name|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState.Checked>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margen|`0, 0, 0, 0`|  
    |Relleno|`3, 3, 3, 3`|  
    |Texto|**Correo**|  
    |TextAlign|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  Repita el paso 7 para tres más <xref:System.Windows.Forms.ToolStripButton> controles.  
  
     Asigne a los controles `calendarStackButton`, `contactsStackButton`, y `tasksStackButton`. Establezca el valor de la <xref:System.Windows.Forms.Control.Text%2A> propiedad **calendario**, **contactos**, y **tareas**, respectivamente.  
  
## <a name="handling-events"></a>Controlar eventos  
 Dos eventos son importantes para realizar la `StackView` control se comporten correctamente. Controlar la <xref:System.Windows.Forms.UserControl.Load> eventos para colocar el control correctamente. Controlar la <xref:System.Windows.Forms.ToolStripItem.Click> eventos para cada <xref:System.Windows.Forms.ToolStripButton> para dar el `StackView` controlan el comportamiento de estado similar a la <xref:System.Windows.Forms.RadioButton> control.  
  
#### <a name="to-handle-events"></a>Para controlar eventos  
  
1.  En el Diseñador de Windows Forms, seleccione el `StackView` control.  
  
2.  En la ventana **Propiedades**, haga clic en **Eventos**.  
  
3.  Haga doble clic en el evento Load para generar el `StackView_Load` controlador de eventos.  
  
4.  En el controlador de eventos `StackView_Load`, copie y pegue el siguiente código.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  En el Diseñador de Windows Forms, seleccione el `mailStackButton` control.  
  
6.  En la ventana **Propiedades**, haga clic en **Eventos**.  
  
7.  Haga doble clic en el evento Click.  
  
     El Diseñador de formularios de Windows genera el `mailStackButton_Click` controlador de eventos.  
  
8.  Cambiar el nombre de la `mailStackButton_Click` controlador de eventos `stackButton_Click`.  
  
     Para obtener más información, consulte [cambiar el nombre de una refactorización de código símbolos](/visualstudio/ide/reference/rename).  
  
9. Inserte el código siguiente en el `stackButton_Click` controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. En el Diseñador de Windows Forms, seleccione el `calendarStackButton` control.  
  
11. En el **propiedades** ventana, establezca el evento Click en la `stackButton_Click` controlador de eventos.  
  
12. Repita los pasos 10 y 11 para el `contactsStackButton` y `tasksStackButton` controles.  
  
## <a name="defining-icons"></a>Definición de iconos  
 Cada `StackView` botón tiene un icono asociado. Para mayor comodidad, cada icono se representa como una cadena codificada en Base64, que se deserializa antes un <xref:System.Drawing.Bitmap> se crea a partir de él. En un entorno de producción, se almacenan los datos de mapa de bits como un recurso y sus iconos aparecen en el Diseñador de Windows Forms. Para obtener más información, vea [Cómo: Agregar imágenes de fondo a formularios Windows](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).  
  
#### <a name="to-define-icons"></a>Para definir los iconos  
  
1.  En el Editor de código, inserte el código siguiente en el `StackView` definición de clase. Este código inicializa los mapas de bits para el <xref:System.Windows.Forms.ToolStripButton> iconos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Agregue una llamada a la `InitializeImages` método en el `StackView` constructor de clase.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a>Implementación de un representador personalizado  
 Puede personalizar la mayoría de los elementos de la `StackView` controlar implementando una clase que deriva la <xref:System.Windows.Forms.ToolStripRenderer> clase. En este procedimiento, implementará un <xref:System.Windows.Forms.ToolStripProfessionalRenderer> clase que personaliza el control y dibuja los fondos de degradado para el <xref:System.Windows.Forms.ToolStripButton> controles.  
  
#### <a name="to-implement-a-custom-renderer"></a>Para implementar a un representador personalizado  
  
1.  Inserte el código siguiente en el `StackView` controlar la definición.  
  
     Se trata de la definición de la `StackRenderer` clase, lo que invalida el <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, y <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> métodos para producir una apariencia personalizada.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  En el `StackView` constructor del control, cree una nueva instancia de la `StackRenderer` clase y asignar esta instancia con el `stackStrip` del control <xref:System.Windows.Forms.ToolStrip.Renderer%2A> propiedad.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a>Probar el Control StackView  
 El `StackView` control se deriva de la <xref:System.Windows.Forms.UserControl> clase. Por lo tanto, puede probar el control con el **UserControl Test Container**. Para obtener más información, vea [Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### <a name="to-test-the-stackview-control"></a>Para probar el control StackView  
  
1.  Presione F5 para compilar el proyecto e iniciar el **UserControl Test Container**.  
  
2.  Mueva el puntero sobre los botones de la `StackView` controlar y, a continuación, haga clic en un botón para ver el aspecto de su estado seleccionado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 En este tutorial, ha creado un control de cliente personalizado reutilizable con el aspecto de un control de Office XP professional. Puede usar el <xref:System.Windows.Forms.ToolStrip> familia de controles para muchos otros objetivos:  
  
-   Crear menús contextuales para los controles con <xref:System.Windows.Forms.ContextMenuStrip>. Para obtener más información, consulte [información general del componente ContextMenu](contextmenu-component-overview-windows-forms.md).  
  
-   Crear un formulario con un menú estándar rellenado automáticamente. Para obtener más información, vea [Tutorial: Proporcionar elementos de menú estándar a un formulario](walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Crear un formulario de múltiples documentos (MDI) de la interfaz con acoplamiento <xref:System.Windows.Forms.ToolStrip> controles. Para obtener más información, vea [Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [ToolStrip](toolstrip-control-windows-forms.md)
- [Filtrar para proporcionar elementos de menú estándar a un formulario](how-to-provide-standard-menu-items-to-a-form.md)
