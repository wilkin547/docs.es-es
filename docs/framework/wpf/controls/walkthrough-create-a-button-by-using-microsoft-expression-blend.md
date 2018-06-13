---
title: 'Tutorial: Crear un botón mediante Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 55585aba8f734b4796c7ba63bcb840acac2c58c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558023"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Tutorial: Crear un botón mediante Microsoft Expression Blend
Este tutorial le guía a través del proceso de creación de un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] botón personalizado mediante Microsoft Expression Blend.  
  
> [!IMPORTANT]
>  Microsoft Expression Blend funciona generando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que, a continuación, se compila para crear el programa ejecutable. Si prefiere trabajar con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] directamente, hay otro tutorial que crea la misma aplicación como uno con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] con Visual Studio, en lugar de Blend. Vea [crear un botón mediante el uso de XAML](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md) para obtener más información.  
  
 En la siguiente ilustración muestra el botón personalizado que va a crear.  
  
 ![Botón personalizado que creará](../../../../docs/framework/wpf/controls/media/custom-button-blend-intro.jpg "custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Convertir una forma en un botón  
 En la primera parte de este tutorial creará el aspecto personalizado del botón personalizado. Para ello, primero convertir un rectángulo en un botón. A continuación, agregará formas adicionales a la plantilla del botón, crear un botón con un aspecto más complejo. ¿Por qué no comience con un botón normal y personalizarlo? Dado que un botón tiene una funcionalidad integrada que no es necesario; para los botones personalizados, es más fácil empezar por un rectángulo.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Para crear un nuevo proyecto en Expression Blend  
  
1.  Inicie Expression Blend. (Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft Expression**y, a continuación, haga clic en **Microsoft Expression Blend**.)  
  
2.  Maximice la aplicación si es necesario.  
  
3.  En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
4.  Seleccione **aplicación estándar (.exe)**.  
  
5.  Denomine el proyecto `CustomButton` y presione **Aceptar**.  
  
 En este punto tiene un espacio en blanco [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proyecto. También puede presionar F5 para ejecutar la aplicación. Como cabría esperar, la aplicación está formada por solo una ventana en blanco. A continuación, crear un rectángulo redondeado y convertirlo en un botón.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Para convertir un rectángulo en un botón  
  
1.  **Establezca la propiedad de fondo de la ventana en negro:** seleccione la ventana, haga clic en el **ficha propiedades**y establezca el <xref:System.Windows.Controls.Control.Background%2A> propiedad `Black`.  
  
     ![Cómo establecer el fondo de un botón en negro](../../../../docs/framework/wpf/controls/media/custom-button-blend-changebackground.png "custom_button_blend_ChangeBackground")  
  
2.  **Dibuja un rectángulo aproximadamente el tamaño de un botón en la ventana:** seleccionar la herramienta rectángulo en el panel izquierdo de herramienta y arrastre el rectángulo a la ventana.  
  
     ![Cómo dibujar un rectángulo](../../../../docs/framework/wpf/controls/media/custom-button-blend-drawrect.png "custom_button_blend_DrawRect")  
  
3.  **Completan los vértices del rectángulo:** los puntos de control del rectángulo de arrastre o establecer directamente la <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades. Establecer los valores de <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> a 20.  
  
     ![Cómo hacer que las esquinas de un rectángulo redondeado](../../../../docs/framework/wpf/controls/media/custom-button-blend-roundcorners.png "custom_button_blend_RoundCorners")  
  
4.  **Cambiar el rectángulo en un botón:** seleccione el rectángulo. En el **herramientas** menú, haga clic en **Crear botón**.  
  
     ![Cómo convertir una forma en un botón](../../../../docs/framework/wpf/controls/media/custom-button-blend-makebutton.png "custom_button_blend_MakeButton")  
  
5.  **Especificar el ámbito de la plantilla de estilo:** un cuadro de diálogo que aparece lo siguiente.  
  
     ![El cuadro de diálogo "Create Style Resource"](../../../../docs/framework/wpf/controls/media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     Para **nombre de recurso (clave)**, seleccione **aplicar a todos los**.  Esto hará que el estilo resultante y la plantilla de botón que se aplican a todos los objetos que son botones. Para **definir en**, seleccione **aplicación**. Esto hará que el estilo resultante y la plantilla de botón tienen ámbito sobre toda la aplicación. Al establecer los valores de estos dos cuadros, el estilo de botón y la plantilla se aplican a todos los botones en toda la aplicación y cualquier botón que cree en la aplicación utilizará, de forma predeterminada, esta plantilla.  
  
## <a name="edit-the-button-template"></a>Edite la plantilla de botón  
 Ahora dispone de un rectángulo que se ha cambiado a un botón. En esta sección, podrá modificar la plantilla del botón y personalizar aún más su aspecto.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>Para editar la plantilla de botón para cambiar la apariencia del botón  
  
1.  **Vaya a la vista de edición de plantillas:** para personalizar aún más la apariencia del botón de nuestra, necesitamos editar la plantilla de botón. Esta plantilla se creó al convertir el rectángulo en un botón. Para editar la plantilla del botón, haga clic en el botón y seleccione **Editar partes del Control (plantilla)** y, a continuación, **Editar plantilla**.  
  
     ![Cómo editar una plantilla de](../../../../docs/framework/wpf/controls/media/custom-button-blend-edittemplate.jpg "custom_button_blend_EditTemplate")  
  
     En el editor de plantillas, tenga en cuenta que el botón se divide ahora en un <xref:System.Windows.Shapes.Rectangle> y <xref:System.Windows.Controls.ContentPresenter>. El <xref:System.Windows.Controls.ContentPresenter> se utiliza para presentar contenido en el botón (por ejemplo, la cadena "Button"). Tanto el rectángulo y <xref:System.Windows.Controls.ContentPresenter> están dispuestos dentro de un <xref:System.Windows.Controls.Grid>.  
  
     ![Componentes de la presentación de un rectángulo](../../../../docs/framework/wpf/controls/media/custom-button-blend-templatepanel.png "custom_button_blend_TemplatePanel")  
  
2.  **Cambiar los nombres de los componentes de plantilla:** haga clic en el rectángulo en el inventario de plantilla, cambiar el <xref:System.Windows.Shapes.Rectangle> nombre desde "[rectángulo]" para "RectánguloExterior" y cambiar "[ContentPresenter]" a "MiContentPresenter".  
  
     ![Cómo cambiar el nombre de un componente de una plantilla de](../../../../docs/framework/wpf/controls/media/custom-button-blend-renamecomponents.png "custom_button_blend_RenameComponents")  
  
3.  **Modificar el rectángulo para que esté vacío dentro de (por ejemplo, un anillo):** seleccione **RectánguloExterior** y establecer <xref:System.Windows.Shapes.Shape.Fill%2A> en "Transparent" y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> a 5.  
  
     ![Cómo crear un rectángulo vacío](../../../../docs/framework/wpf/controls/media/custom-button-blend-changerectproperties.png "custom_button_blend_ChangeRectProperties")  
  
     A continuación, establezca el <xref:System.Windows.Shapes.Shape.Stroke%2A> el color de lo que será la plantilla. Para ello, haga clic en el pequeño cuadro blanco junto al **trazo**, seleccione **expresión personalizada**y escriba "{fondo de TemplateBinding}" en el cuadro de diálogo.  
  
     ![Cómo establecer el uso del color de la plantilla de](../../../../docs/framework/wpf/controls/media/custom-button-blend-templatestroke.png "custom_button_blend_TemplateStroke")  
  
4.  **Crear un rectángulo interno:** ahora, cree otro rectángulo (asígnele el nombre "RectánguloInterior") y ubíquelo simétricamente en el interior de **RectánguloExterior** . Para este tipo de trabajo, probablemente deseará ajustar el zoom para ampliar el botón en el área de edición.  
  
    > [!NOTE]
    >  El rectángulo podría ser diferente de la que se muestra en la ilustración (por ejemplo, podrían haber esquinas redondeadas).  
  
     ![Cómo crear un rectángulo dentro de otro](../../../../docs/framework/wpf/controls/media/custom-button-blend-innerrectangleproperties.png "custom_button_blend_innerRectangleProperties")  
  
5.  **Mueva ContentPresenter a la parte superior:** en este punto, es posible que el texto "Button" no será visible ya. Si es así, esto es porque **RectánguloInterior** está en la parte superior de la **MiContentPresenter**. Para solucionar este problema, arrastre **MiContentPresenter** a continuación **RectánguloInterior**. Cambiar la posición de los rectángulos y **MiContentPresenter** a un aspecto parecido al siguiente.  
  
    > [!NOTE]
    >  Como alternativa, también puede colocar **MiContentPresenter** en la parte superior haciendo clic en él y presionando **enviar al día**.  
  
     ![Cómo mover un botón encima de otro botón](../../../../docs/framework/wpf/controls/media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6.  **Cambiar el aspecto de RectánguloInterior:** establecer el <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> valores a 20. In Addition, establezca el <xref:System.Windows.Shapes.Shape.Fill%2A> al fondo de la plantilla utilizando la expresión personalizada "{fondo de TemplateBinding}") y establezca <xref:System.Windows.Shapes.Shape.Stroke%2A> en "transparent". Tenga en cuenta que la configuración de la <xref:System.Windows.Shapes.Shape.Fill%2A> y <xref:System.Windows.Shapes.Shape.Stroke%2A> de **RectánguloInterior** son los opuestos a los de **RectánguloExterior**.  
  
     ![Cómo cambiar la apariencia de un rectángulo](../../../../docs/framework/wpf/controls/media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7.  **Agregar una capa de cristal en la parte superior:** es el último fragmento de personalizar la apariencia del botón Agregar una capa de cristal en la parte superior. Esta capa de cristal consta de un tercer rectángulo. Dado que el cristal cubrirá todo el botón, el rectángulo de cristal es similar en las dimensiones a la **RectánguloExterior**. Por lo tanto, crear el rectángulo basta con realizar una copia de la **RectánguloExterior**. Resaltar **RectánguloExterior** y use CTRL+C y CTRL+V para realizar una copia. Nombre de este nuevo rectángulo "glassCube".  
  
8.  **Cambiar la posición de glassCube si es necesario:** si **glassCube** es aún no está colocado modo que cubra todo el botón, arrástrela hasta su posición.  
  
9. **Proporcionan una forma ligeramente diferente a RectánguloExterior de glassCube:** cambiar las propiedades de **glassCube**. Comience cambiando el <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades a 10 y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> a 2.  
  
     ![La configuración de apariencia de glassCube](../../../../docs/framework/wpf/controls/media/custom-button-blend-glasscubeappearance.gif "custom_button_blend_GlassCubeAppearance")  
  
10. **Asegúrese de glassCube el aspecto de cristal:** establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> a un vistazo ello mediante el uso de un degradado lineal que es el 75% opaco y alterna entre el color blanco y transparente en 6 aproximadamente uniformemente espaciados intervalos. Esto es lo que se debe establecer los delimitadores de degradado:  
  
    -   Delimitador de degradado 1: Blanco con valor alfa del 75%  
  
    -   Delimitador de degradado 2: transparente  
  
    -   Delimitador de degradado 3: Blanco con valor alfa del 75%  
  
    -   Delimitador de degradado 4: transparente  
  
    -   Delimitador de degradado 5: Blanco con valor alfa del 75%  
  
    -   6 de degradado: transparente  
  
     Esto crea un aspecto de cristal "ondulado".  
  
     ![Un rectángulo que apariencia de cristal](../../../../docs/framework/wpf/controls/media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Ocultar la capa de cristal:** ahora que ha visto el aspecto de la capa de ello, vaya a la **panel apariencia** de la **panel de propiedades de** y establezca la opacidad a 0% para ocultarlo. En las secciones siguientes, utilizaremos desencadenadores de propiedad y eventos para mostrar y manipular la capa de cristal.  
  
     ![Cómo ocultar el rectángulo de cristal](../../../../docs/framework/wpf/controls/media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Personalizar el comportamiento del botón  
 En este momento, ha personalizado la presentación del botón editando su plantilla, pero el botón no reacciona a las acciones del usuario como botones habituales (por ejemplo, cambiando su aspecto al pasar el mouse, recibe el foco y haga clic en.) Los dos procedimientos siguientes muestran cómo crear comportamientos como estos elementos en el botón personalizado. Se podrá iniciar con desencadenadores de propiedad simple y, a continuación, agregue las animaciones y los desencadenadores de eventos.  
  
#### <a name="to-set-property-triggers"></a>Para establecer la propiedad triggers  
  
1.  **Crear un nuevo desencadenador de propiedad:** con **glassCube** seleccionado, haga clic en **+ propiedad** en el **desencadenadores** panel (Véase la figura que sigue el paso siguiente). Esto crea un desencadenador de propiedad con un desencadenador de propiedad predeterminado.  
  
2.  **Convierta la propiedad usada por el desencadenador en IsMouseOver:** cambie la propiedad a <xref:System.Windows.UIElement.IsMouseOver%2A>. Esto hace que el desencadenador de la propiedad activar cuando la <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad es `true` (cuando el usuario elige el botón con el mouse).  
  
     ![Cómo establecer un desencadenador en una propiedad](../../../../docs/framework/wpf/controls/media/custom-button-blend-ismousedoverpropertytrigger.png "custom_button_blend_IsMousedOverPropertyTrigger")  
  
3.  **IsMouseOver desencadena la opacidad del 100% de glassCube:** tenga en cuenta que la **grabación de desencadenador es en** (vea la ilustración anterior). Esto significa que los cambios que realice a los valores de propiedad de **glassCube** mientras se está grabando en se convertirá en una acción que se lleva a cabo cuando <xref:System.Windows.UIElement.IsMouseOver%2A> es `true`. Durante la grabación, cambie la <xref:System.Windows.UIElement.Opacity%2A> de **glassCube** al 100%.  
  
     ![Cómo establecer la opacidad de un botón de](../../../../docs/framework/wpf/controls/media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     Ahora ha creado su primer desencadenador de propiedad. Tenga en cuenta que la **panel desencadenadores** del editor ha grabado el <xref:System.Windows.UIElement.Opacity%2A> está cambiando a 100%.  
  
     ![El panel "Desencadenadores"](../../../../docs/framework/wpf/controls/media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Presione F5 para ejecutar la aplicación y mover el puntero del mouse sobre y desactivar el botón. Debería ver que la capa de cristal aparecen cuando el botón del mouse y desaparecen cuando el puntero sale.  
  
4.  **Desencadenadores de IsMouseOver trazar el cambio del valor:** permite asociar algunas otras acciones con el <xref:System.Windows.UIElement.IsMouseOver%2A> desencadenador. Mientras la grabación continúa, cambie la selección de **glassCube** a **RectánguloExterior**. A continuación, establezca el <xref:System.Windows.Shapes.Shape.Stroke%2A> de **RectánguloExterior** en la expresión personalizada "{DynamicResource {x: Static SystemColors.HighlightBrushKey}}". Esto establece el <xref:System.Windows.Shapes.Shape.Stroke%2A> utilizada botones de color de resaltado de para típica. Presione F5 para ver el efecto cuando desplaza el mouse sobre el botón.  
  
     ![Cómo establecer el trazo en el color de resaltado](../../../../docs/framework/wpf/controls/media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5.  **IsMouseOver desencadena texto borroso:** permite asociar una acción más a la <xref:System.Windows.UIElement.IsMouseOver%2A> desencadenador de propiedad. Poner el contenido del botón se vea un poco borroso cuando el cristal aparezca sobre él. Para ello, podemos aplicar un desenfoque <xref:System.Windows.Media.Effects.BitmapEffect> a la <xref:System.Windows.Controls.ContentPresenter> (**MiContentPresenter**).  
  
     ![Cómo difuminar el contenido de un botón de](../../../../docs/framework/wpf/controls/media/custom-button-blend-propertytriggerwithbitmapeffect.png "custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    >  Para devolver el **panel Propiedades** vuelve a su estado antes de iniciar la búsqueda de <xref:System.Windows.Media.Effects.BitmapEffect>, borre el texto de la **cuadro de búsqueda**.  
  
     En este punto, hemos utilizado un desencadenador de propiedad con varias acciones asociadas para crear el comportamiento de resaltado cuando el puntero del mouse entra y sale del área de botón. Otro comportamiento típico de un botón es permanecer resaltado cuando tiene el foco (como ocurre cuando se hace clic). Podemos agregar dicho comportamiento agregando otro desencadenador de propiedad para el <xref:System.Windows.UIElement.IsFocused%2A> propiedad.  
  
6.  **Crear el desencadenador de propiedad para IsFocused:** con el mismo procedimiento que para <xref:System.Windows.UIElement.IsMouseOver%2A> (vea el primer paso de esta sección), cree otro desencadenador de propiedad para el <xref:System.Windows.UIElement.IsFocused%2A> propiedad. Mientras **grabación de desencadenador que se encuentra en**, agregue lo siguiente al desencadenador:  
  
    -   **glassCube** Obtiene un <xref:System.Windows.UIElement.Opacity%2A> del 100%.  
  
    -   **RectánguloExterior** Obtiene un <xref:System.Windows.Shapes.Shape.Stroke%2A> valor de expresión personalizada "{DynamicResource {x: Static SystemColors.HighlightBrushKey}}".  
  
 Como último paso en este tutorial, agregaremos las animaciones en el botón. Estas animaciones se activará por eventos, en concreto, el <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Usar desencadenadores de eventos y las animaciones para agregar interactividad  
  
1.  **Crear un desencadenador de evento MouseEnter:** agregar un nuevo desencadenador de evento y seleccione <xref:System.Windows.UIElement.MouseEnter> como el evento para usar en el desencadenador.  
  
     ![Cómo crear un desencadenador de evento MouseEnter](../../../../docs/framework/wpf/controls/media/custom-button-blend-mouseovereventtrigger.png "custom_button_blend_MouseOverEventTrigger")  
  
2.  **Crear una escala de tiempo de animación:** a continuación, asociar una escala de tiempo de animación para la <xref:System.Windows.UIElement.MouseEnter> eventos.  
  
     ![Cómo agregar una escala de tiempo de animación a un evento](../../../../docs/framework/wpf/controls/media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Después de presionar **Aceptar** para crear una nueva escala de tiempo, un **Panel de escala de tiempo** aparece y está visible en el panel de diseño "Grabación está en la escala de tiempo". Esto significa que podemos empezar a grabar cambios de propiedades en la escala de tiempo (animar cambios de propiedades).  
  
    > [!NOTE]
    >  Debe cambiar el tamaño de la ventana o los paneles para ver la presentación.  
  
     ![El panel de escala de tiempo](../../../../docs/framework/wpf/controls/media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3.  **Crear un fotograma clave:** para crear una animación, seleccione el objeto que desea animar, cree dos o más fotogramas clave en la escala de tiempo y para los fotogramas clave, establezca los valores de propiedad que desea que la animación se interpolará entre. La ilustración siguiente le guía a través de la creación de un fotograma clave.  
  
     ![Cómo crear un fotograma clave](../../../../docs/framework/wpf/controls/media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4.  **Reducir glassCube en este fotograma clave:** con el segundo fotograma clave seleccionado, reducir el tamaño de la **glassCube** en el 90% de su tamaño completo mediante el **tamaño transformar**.  
  
     ![Cómo reducir el tamaño de un botón de](../../../../docs/framework/wpf/controls/media/custom-button-blend-sizetransform.png "custom_button_blend_SizeTransform")  
  
     Presione F5 para ejecutar la aplicación. Mueva el puntero del mouse sobre el botón. Tenga en cuenta que la capa de cristal se reduce en la parte superior del botón.  
  
5.  **Cree otro desencadenador de eventos y asocie una animación diferentes:** agreguemos una animación más. Utilice un procedimiento similar al que utilizó para crear la animación de desencadenador de eventos anterior:  
  
    1.  Crear un nuevo desencadenador de evento con el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
    2.  Asociar una nueva escala de tiempo con el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
     ![Cómo crear una nueva escala de tiempo](../../../../docs/framework/wpf/controls/media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1.  Para esta escala de tiempo, cree dos fotogramas clave, uno a los 0,0 segundos y el otro a los 0,3 segundos.  
  
    2.  Con el fotograma clave en 0,3 segundos resaltado, establezca el **ángulo de giro** a 360 grados.  
  
     ![Cómo crear una transformación de giro](../../../../docs/framework/wpf/controls/media/custom-button-blend-rotatetransform.gif "custom_button_blend_RotateTransform")  
  
    1.  Presione F5 para ejecutar la aplicación. Haga clic en el botón. Observe que la capa de cristal gira sobre sí mismo.  
  
## <a name="conclusion"></a>Conclusión  
 Ha completado un botón personalizado. Ello, ha utilizado una plantilla de botón que se aplica a todos los botones de la aplicación. Si deja el modo de edición de plantillas (vea la figura siguiente) y crea más botones, verá que se parecen y se comportan como el botón personalizado en lugar de como el botón predeterminado.  
  
 ![La plantilla de botón personalizado](../../../../docs/framework/wpf/controls/media/custom-button-blend-scopeup.gif "custom_button_blend_ScopeUp")  
  
 ![Varios botones que usan la misma plantilla](../../../../docs/framework/wpf/controls/media/custom-button-blend-createmultiplebuttons.png "custom_button_blend_CreateMultipleButtons")  
  
 Presione F5 para ejecutar la aplicación. Haga clic en los botones y observe cómo todos ellos comportan del mismo.  
  
 Recuerde que mientras estaba personalizando la plantilla, define la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de **RectánguloInterior** y <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad **RectánguloExterior** para el fondo de plantilla ({} Fondo de TemplateBinding}). Por este motivo, cuando se establece el color de fondo de los botones individuales, el fondo que estableció se utilizará para las propiedades respectivas. Pruebe a cambiar los fondos ahora. En la ilustración siguiente, se utilizan distintos degradados. Por lo tanto, aunque una plantilla es útil para una personalización global de controles como los botones, controles basados en plantillas aún pueden modificarse para que sean distintos entre sí.  
  
 ![Botones con la misma plantilla que tengan un aspecto diferente](../../../../docs/framework/wpf/controls/media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")  
  
 En conclusión, en el proceso de personalización de una plantilla de botón ha aprendido a hacer lo siguiente en Microsoft Expression Blend:  
  
-   Personalizar la apariencia de un control.  
  
-   Establecer desencadenadores de propiedad. Desencadenadores de propiedad resultan muy útiles porque se puede usar en la mayoría de los objetos, no sólo en los controles.  
  
-   Establecer desencadenadores de eventos. Desencadenadores de eventos son muy útiles porque pueden usarse en la mayoría de los objetos, no sólo en los controles.  
  
-   Crear animaciones.  
  
-   Varios: crear degradados, agregar BitmapEffects, utilizar las transformaciones y establecer propiedades básicas de los objetos.  
  
## <a name="see-also"></a>Vea también  
 [Crear un botón mediante el uso de XAML](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-xaml.md)  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre el dibujo con colores sólidos y degradados](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Información general sobre efectos de imagen](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
