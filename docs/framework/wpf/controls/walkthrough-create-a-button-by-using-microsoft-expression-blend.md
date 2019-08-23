---
title: 'Tutorial: Crear un botón mediante Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 1b4c775ea0680dcd8252a98c722dfe8f7e62548f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942502"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Tutorial: Crear un botón mediante Microsoft Expression Blend
Este tutorial le guiará por el proceso de creación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] de un botón personalizado mediante Microsoft Expression Blend.  
  
> [!IMPORTANT]
> Microsoft Expression Blend genera [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y, a continuación, se compila para crear el programa ejecutable. Si prefiere trabajar con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] directamente, hay otro tutorial que crea la misma aplicación que esta usando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] con Visual Studio en lugar de Blend. Para obtener más información [, vea crear un botón mediante XAML](walkthrough-create-a-button-by-using-xaml.md) .  
  
 En la ilustración siguiente se muestra el botón personalizado que creará.  
  
 ![Botón personalizado que va a crear] . (./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Convertir una forma en un botón  
 En la primera parte de este tutorial, creará la apariencia personalizada del botón personalizado. Para ello, primero debe convertir un rectángulo en un botón. A continuación, agregue formas adicionales a la plantilla del botón, creando un botón de aspecto más complejo. ¿Por qué no empezar con un botón normal y personalizarlo? Dado que un botón tiene una funcionalidad integrada que no necesita; en el caso de los botones personalizados, es más fácil empezar con un rectángulo.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Para crear un nuevo proyecto en Expression Blend  
  
1. Iniciar Expression Blend. (Haga clic en **Inicio**, seleccione **todos los programas**, elija **Microsoft Expression**y, a continuación, haga clic en **Microsoft Expression Blend**).  
  
2. Maximice la aplicación si es necesario.  
  
3. En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
4. Seleccione **aplicación estándar (. exe)** .  
  
5. Asigne un nombre `CustomButton` al proyecto y haga clic en **Aceptar**.  
  
 En este momento tiene un proyecto en [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] blanco. Puede presionar F5 para ejecutar la aplicación. Como cabría esperar, la aplicación solo se compone de una ventana en blanco. A continuación, se crea un rectángulo redondeado y se convierte en un botón.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Para convertir un rectángulo en un botón  
  
1. **Establezca la propiedad fondo de la ventana en negro:** Seleccione la ventana, haga clic en la **pestaña propiedades**y establezca <xref:System.Windows.Controls.Control.Background%2A> la propiedad `Black`en.  
  
     ![Cómo establecer el fondo de un botón en negro](./media/custom-button-blend-changebackground.png "custom_button_blend_ChangeBackground")  
  
2. **Dibuja un rectángulo aproximadamente el tamaño de un botón en la ventana:** Seleccione la herramienta rectángulo en el panel de herramientas de la izquierda y arrastre el rectángulo a la ventana.  
  
     ![Cómo dibujar un rectángulo](./media/custom-button-blend-drawrect.png "custom_button_blend_DrawRect")  
  
3. **Redondear las esquinas del rectángulo:** Arrastre los puntos de control del rectángulo o establezca directamente las <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> propiedades y. <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> Establezca los valores de <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> en 20.  
  
     ![Cómo hacer que las esquinas de un rectángulo] se redondeen (./media/custom-button-blend-roundcorners.png "custom_button_blend_RoundCorners")  
  
4. **Cambie el rectángulo a un botón:** Seleccione el rectángulo. En el menú **herramientas** , haga clic en el **botón crear**.  
  
     ![Cómo convertir una forma en un botón](./media/custom-button-blend-makebutton.png "custom_button_blend_MakeButton")  
  
5. **Especifique el ámbito del estilo o la plantilla:** Aparece un cuadro de diálogo como el siguiente.  
  
     ![Cuadro de diálogo "crear recurso de estilo"](./media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     En **nombre de recurso (clave)** , seleccione **aplicar a todo**.  Esto hará que el estilo y la plantilla de botón resultantes se apliquen a todos los objetos que son botones. **En definir en**, seleccione **aplicación**. Esto hará que el estilo y la plantilla de botón resultantes tengan el ámbito en toda la aplicación. Al establecer los valores de estos dos cuadros, el estilo de botón y la plantilla se aplican a todos los botones de la aplicación completa y cualquier botón que se cree en la aplicación usará de forma predeterminada esta plantilla.  
  
## <a name="edit-the-button-template"></a>Editar la plantilla de botón  
 Ahora tiene un rectángulo que se ha cambiado a un botón. En esta sección, modificará la plantilla del botón y personalizará aún más su aspecto.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>Para editar la plantilla de botón para cambiar la apariencia del botón  
  
1. **Vaya a Editar vista de plantilla:** Para personalizar aún más el aspecto de nuestro botón, es necesario editar la plantilla de botón. Esta plantilla se creó cuando se convirtió el rectángulo en un botón. Para editar la plantilla de botón, haga clic con el botón derecho en el botón y seleccione **Editar partes de control (plantilla)** y, a continuación, **Editar plantilla**.  
  
     ![Cómo editar una plantilla](./media/custom-button-blend-edittemplate.jpg "custom_button_blend_EditTemplate")  
  
     En el editor de plantillas, observe que el botón ahora está separado en <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.Controls.ContentPresenter>y. <xref:System.Windows.Controls.ContentPresenter> Se utiliza para presentar el contenido dentro del botón (por ejemplo, la cadena "Button"). Ambos rectángulos y <xref:System.Windows.Controls.ContentPresenter> se colocan dentro de <xref:System.Windows.Controls.Grid>un.  
  
     ![Componentes de la presentación de un rectángulo](./media/custom-button-blend-templatepanel.png "custom_button_blend_TemplatePanel")  
  
2. **Cambie los nombres de los componentes de la plantilla:** Haga clic con el botón secundario en el rectángulo en el inventario <xref:System.Windows.Shapes.Rectangle> de la plantilla, cambie el nombre de "[Rectangle]" a "outerRectangle" y cambie "[ContentPresenter]" por "myContentPresenter".  
  
     ![Cómo cambiar el nombre de un componente de una plantilla](./media/custom-button-blend-renamecomponents.png "custom_button_blend_RenameComponents")  
  
3. **Modifique el rectángulo para que esté vacío dentro de (como un anillo):** Seleccione **outerRectangle** y establezca <xref:System.Windows.Shapes.Shape.Fill%2A> en "transparente" y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> en 5.  
  
     ![Cómo hacer que un rectángulo esté vacío](./media/custom-button-blend-changerectproperties.png "custom_button_blend_ChangeRectProperties")  
  
     A continuación, <xref:System.Windows.Shapes.Shape.Stroke%2A> establezca el valor de en el color de lo que vaya a ser la plantilla. Para ello, haga clic en el cuadro blanco pequeño situado junto a **Stroke**, seleccione **CustomExpression**y escriba "{background TemplateBinding}" en el cuadro de diálogo.  
  
     ![Cómo establecer el uso del color de la plantilla](./media/custom-button-blend-templatestroke.png "custom_button_blend_TemplateStroke")  
  
4. **Cree un rectángulo interno:** Ahora, cree otro rectángulo (asígnele el nombre "innerRectangle") y colóquelo simétricamente en el interior de **outerRectangle** . Para este tipo de trabajo, es probable que desee hacer zoom para aumentar el tamaño del botón en el área de edición.  
  
    > [!NOTE]
    > El rectángulo podría tener una apariencia diferente a la de la ilustración (por ejemplo, podría tener esquinas redondeadas).  
  
     ![Cómo crear un rectángulo dentro de otro rectángulo](./media/custom-button-blend-innerrectangleproperties.png "custom_button_blend_innerRectangleProperties")  
  
5. **Mueva ContentPresenter a la parte superior:** En este punto, es posible que el texto "Button" no sea visible más. Si es así, esto se debe a que **innerRectangle** está en la parte superior de **myContentPresenter**. Para solucionarlo, arrastre **myContentPresenter** debajo de **innerRectangle**. Cambie la posición de los rectángulos y **myContentPresenter** para que tengan un aspecto similar al siguiente.  
  
    > [!NOTE]
    > También puede colocar **myContentPresenter** en la parte superior haciendo clic con el botón derecho en él y presionando **enviar hacia delante**.  
  
     ![Cómo desplace un botón encima de otro botón](./media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6. **Cambiar el aspecto de innerRectangle:** Establezca los <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>valores <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> en 20. Además, establezca <xref:System.Windows.Shapes.Shape.Fill%2A> en el fondo de la plantilla mediante la expresión personalizada "{background TemplateBinding}") y establézcalo <xref:System.Windows.Shapes.Shape.Stroke%2A> en "transparent". Observe <xref:System.Windows.Shapes.Shape.Fill%2A> que los valores de y <xref:System.Windows.Shapes.Shape.Stroke%2A> de **innerRectangle** son los opuestos a los de **outerRectangle**.  
  
     ![Cómo cambiar la apariencia de un rectángulo](./media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7. **Agregar una capa de cristal en la parte superior:** La parte final de la personalización de la apariencia del botón es agregar una capa de cristal en la parte superior. Esta capa de cristal está formada por un tercer rectángulo. Dado que el cristal cubre todo el botón, el rectángulo de cristal es similar en dimensiones al **outerRectangle**. Por lo tanto, cree el rectángulo simplemente haciendo una copia de **outerRectangle**. Resalte **outerRectangle** y use Ctrl + C y Ctrl + V para hacer una copia. Asigne a este nuevo rectángulo el nombre "glassCube".  
  
8. **Cambie la posición de glassCube si es necesario:** Si **glassCube** no está ya situado para que cubra todo el botón, arrástrelo a la posición.  
  
9. **Proporcione a glassCube una forma ligeramente diferente que outerRectangle:** Cambie las propiedades de **glassCube**. Para empezar, cambie las <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> propiedades <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> y a 10 y a 2.  
  
     ![La configuración de la apariencia de glassCube](./media/custom-button-blend-glasscubeappearance.gif "custom_button_blend_GlassCubeAppearance")  
  
10. **Haga que glassCube tenga el aspecto de cristal:** <xref:System.Windows.Shapes.Shape.Fill%2A> Establezca en una apariencia de vidrio con un degradado lineal que sea 75% opaco y alterne entre el color blanco y el transparente en 6 intervalos de aproximadamente espaciados uniformemente. Este es el conjunto de delimitadores de degradado:  
  
    - Detención de degradado 1: Blanco con valor alfa de 75%  
  
    - Detención de degradado 2: Transparente  
  
    - Detención de degradado 3: Blanco con valor alfa de 75%  
  
    - Detención de degradado 4: Transparente  
  
    - Detención de degradado 5: Blanco con valor alfa de 75%  
  
    - Detención de degradado 6: Transparente  
  
     Esto crea un aspecto de cristal "ondulado".  
  
     ![Rectángulo que tiene el aspecto de cristal](./media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Ocultar la capa de cristal:** Ahora que ve el aspecto de la capa de cristal, vaya al **Panel apariencia** del **panel Propiedades** y establezca la opacidad en 0% para ocultarla. En las secciones posteriores, usaremos desencadenadores de propiedad y eventos para mostrar y manipular la capa de cristal.  
  
     ![Cómo ocultar el rectángulo de cristal](./media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Personalizar el comportamiento del botón  
 En este punto, ha personalizado la presentación del botón mediante la edición de su plantilla, pero el botón no reacciona a las acciones del usuario como hacen los botones típicos (por ejemplo, cambiar la apariencia al pasar el puntero del mouse, recibir el foco y hacer clic). Los dos procedimientos siguientes muestran cómo compilar comportamientos como estos en el botón personalizado. Comenzaremos con desencadenadores de propiedades simples y, a continuación, agregaremos desencadenadores de eventos y animaciones.  
  
#### <a name="to-set-property-triggers"></a>Para establecer los desencadenadores de propiedad  
  
1. **Cree un nuevo desencadenador de propiedad:** Con **glassCube** seleccionado, haga clic en **+ propiedad** en el panel **desencadenadores** (vea la figura que sigue al paso siguiente). Esto crea un desencadenador de propiedad con un desencadenador de propiedad predeterminado.  
  
2. **Convierta IsMouseOver en la propiedad utilizada por el desencadenador:** Cambie la propiedad a <xref:System.Windows.UIElement.IsMouseOver%2A>. Esto hace que el desencadenador de propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> se active `true` cuando la propiedad es (cuando el usuario apunta al botón con el mouse).  
  
     ![Cómo establecer un desencadenador en una propiedad](./media/custom-button-blend-ismousedoverpropertytrigger.png "custom_button_blend_IsMousedOverPropertyTrigger")  
  
3. **IsMouseOver desencadena la opacidad del 100% para glassCube:** Observe que la **grabación del desencadenador está activada** (vea la ilustración anterior). Esto significa que cualquier cambio que realice en los valores de propiedad de **glassCube** mientras la grabación está activado se convertirá en una acción <xref:System.Windows.UIElement.IsMouseOver%2A> que `true`tendrá lugar cuando sea. Durante la grabación, cambie <xref:System.Windows.UIElement.Opacity%2A> el de **glassCube** a 100%.  
  
     ![Cómo establecer la opacidad de un botón](./media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     Ahora ha creado su primer desencadenador de propiedad. Observe que en el **Panel desencadenadores** del editor se ha registrado <xref:System.Windows.UIElement.Opacity%2A> el cambio a 100%.  
  
     ![El panel "Desencadenadores"](./media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Presione F5 para ejecutar la aplicación y mueva el puntero del mouse sobre el botón y desactívelo. Debería ver que la capa de cristal aparece al pasar el puntero del mouse por encima del botón y desaparece cuando el puntero sale.  
  
4. **Los desencadenadores IsMouseOver cambian el valor del trazo:** Vamos a asociar algunas otras acciones con <xref:System.Windows.UIElement.IsMouseOver%2A> el desencadenador. Mientras continúa la grabación, cambie la selección de **glassCube** a **outerRectangle**. A continuación, <xref:System.Windows.Shapes.Shape.Stroke%2A> establezca el valor de de **outerRectangle** en la expresión personalizada de "{DynamicResource {x:Static SystemColors. HighlightBrushKey}}". Esto establece <xref:System.Windows.Shapes.Shape.Stroke%2A> en el color de resaltado típico utilizado por los botones. Presione F5 para ver el efecto al pasar el puntero sobre el botón.  
  
     ![Cómo establecer el trazo en el color] de resaltado (./media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5. **IsMouseOver desencadena texto borroso:** Vamos a asociar una acción más al <xref:System.Windows.UIElement.IsMouseOver%2A> desencadenador de propiedad. Haga que el contenido del botón parezca un poco borroso cuando aparezca el cristal sobre él. Para ello, podemos aplicar un desenfoque <xref:System.Windows.Media.Effects.BitmapEffect> <xref:System.Windows.Controls.ContentPresenter> a (**myContentPresenter**).  
  
     ![Cómo desenfocar el contenido de un botón](./media/custom-button-blend-propertytriggerwithbitmapeffect.png "custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    > Para devolver el **panel Propiedades** a lo que estaba antes de realizar la búsqueda <xref:System.Windows.Media.Effects.BitmapEffect>, borre el texto del cuadro de **búsqueda**.  
  
     En este punto, se ha usado un desencadenador de propiedad con varias acciones asociadas para crear el comportamiento de resaltado cuando el puntero del Mouse entra y sale del área de botón. Otro comportamiento típico de un botón es resaltar cuando tiene el foco (como después de hacer clic en él). Podemos agregar este comportamiento agregando otro desencadenador de propiedad para <xref:System.Windows.UIElement.IsFocused%2A> la propiedad.  
  
6. **Crear desencadenador de propiedad para IsFocused:** Con el mismo procedimiento que para <xref:System.Windows.UIElement.IsMouseOver%2A> (vea el primer paso de esta sección), cree otro desencadenador de propiedad <xref:System.Windows.UIElement.IsFocused%2A> para la propiedad. Mientras la **grabación del desencadenador está activada**, agregue las siguientes acciones al desencadenador:  
  
    - **glassCube** obtiene un <xref:System.Windows.UIElement.Opacity%2A> de 100%.  
  
    - **outerRectangle** obtiene un <xref:System.Windows.Shapes.Shape.Stroke%2A> valor de expresión personalizado de "{DynamicResource {x:Static SystemColors. HighlightBrushKey}}".  
  
 Como paso final de este tutorial, agregaremos animaciones al botón. Los eventos desencadenarán estas animaciones, en concreto, los <xref:System.Windows.UIElement.MouseEnter> eventos y. <xref:System.Windows.Controls.Primitives.ButtonBase.Click>  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Para usar desencadenadores de eventos y animaciones para agregar interactividad  
  
1. **Cree un desencadenador de evento MouseEnter:** Agregue un nuevo desencadenador de eventos <xref:System.Windows.UIElement.MouseEnter> y seleccione como el evento que se va a usar en el desencadenador.  
  
     ![Cómo crear un desencadenador de evento MouseEnter](./media/custom-button-blend-mouseovereventtrigger.png "custom_button_blend_MouseOverEventTrigger")  
  
2. **Cree una escala de tiempo de animación:** A continuación, asocie una escala de tiempo <xref:System.Windows.UIElement.MouseEnter> de animación al evento.  
  
     ![Cómo agregar una escala de tiempo de animación a un evento](./media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Después de hacer clic en **Aceptar** para crear una nueva escala de tiempo, aparece un **Panel de escala** de tiempo y la "grabación de escala de tiempo está activada" está visible en el panel de diseño. Esto significa que podemos empezar a grabar los cambios de propiedad en la escala de tiempo (animar los cambios de propiedad).  
  
    > [!NOTE]
    > Es posible que tenga que cambiar el tamaño de la ventana o los paneles para ver la pantalla.  
  
     ![Panel de la escala de tiempo](./media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3. **Cree un fotograma clave:** Para crear una animación, seleccione el objeto que desea animar, cree dos o más fotogramas clave en la escala de tiempo y, para esos fotogramas clave, establezca los valores de propiedad entre los que desea que se interpole la animación. La siguiente ilustración le guía a través de la creación de un fotograma clave.  
  
     ![Cómo crear un fotograma clave](./media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4. **Reducir glassCube en este fotograma clave:** Con el segundo fotograma clave seleccionado, reduzca el tamaño del **glassCube** al 90% de su tamaño completo con la **transformación tamaño**.  
  
     ![Cómo reducir el tamaño de un botón](./media/custom-button-blend-sizetransform.png "custom_button_blend_SizeTransform")  
  
     Presione F5 para ejecutar la aplicación. Mueva el puntero del mouse sobre el botón. Observe que la capa de cristal se reduce en la parte superior del botón.  
  
5. **Cree otro desencadenador de eventos y asocie una animación diferente con él:** Vamos a agregar una animación más. Use un procedimiento similar al que usó para crear la animación del desencadenador de evento anterior:  
  
    1. Cree un nuevo desencadenador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> con el evento.  
  
    2. Asociar una nueva escala de <xref:System.Windows.Controls.Primitives.ButtonBase.Click> tiempo al evento.  
  
     ![Cómo crear una nueva escala de tiempo](./media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1. Para esta escala de tiempo, cree dos fotogramas clave, uno en 0,0 segundos y el segundo en 0,3 segundos.  
  
    2. Con el fotograma clave en 0,3 segundos resaltado, establezca el **ángulo de giro** de la transformación en 360 grados.  
  
     ![Cómo crear una transformación de giro](./media/custom-button-blend-rotatetransform.gif "custom_button_blend_RotateTransform")  
  
    1. Presione F5 para ejecutar la aplicación. Haga clic en el botón. Observe que la capa de cristal gira en torno a.  
  
## <a name="conclusion"></a>Conclusión  
 Ha completado un botón personalizado. Lo hizo mediante una plantilla de botón que se aplicó a todos los botones de la aplicación. Si deja el modo de edición de plantillas (vea la ilustración siguiente) y crea más botones, verá que parecen y se comportan como su botón personalizado en lugar de como el botón predeterminado.  
  
 ![La plantilla de botón personalizada](./media/custom-button-blend-scopeup.gif "custom_button_blend_ScopeUp")  
  
 ![Varios botones que usan la misma plantilla](./media/custom-button-blend-createmultiplebuttons.png "custom_button_blend_CreateMultipleButtons")  
  
 Presione F5 para ejecutar la aplicación. Haga clic en los botones y observe cómo se comportan de la misma manera.  
  
 Recuerde que mientras estaba personalizando la plantilla, <xref:System.Windows.Shapes.Shape.Fill%2A> establezca la propiedad de **innerRectangle** y la <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad **outerRectangle** en el fondo de la plantilla ({fondo de TemplateBinding}). Por este motivo, al establecer el color de fondo de los botones individuales, el fondo que establezca se utilizará para las propiedades correspondientes. Intente cambiar el fondo ahora. En la siguiente ilustración, se usan degradados diferentes. Por lo tanto, aunque una plantilla es útil para la personalización global de controles como Button, los controles con plantillas se pueden modificar para que tengan un aspecto diferente.  
  
 ![Botones con la misma plantilla que buscan diferente](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")  
  
 En conclusión, en el proceso de personalización de una plantilla de botón, ha aprendido a hacer lo siguiente en Microsoft Expression Blend:  
  
- Personalizar la apariencia de un control.  
  
- Establezca los desencadenadores de propiedad. Los desencadenadores de propiedad son muy útiles, ya que se pueden usar en la mayoría de los objetos, no solo en los controles.  
  
- Establezca desencadenadores de eventos. Los desencadenadores de eventos son muy útiles, ya que se pueden usar en la mayoría de los objetos, no solo en los controles.  
  
- Crear animaciones.  
  
- Varios: crear degradados, agregar BitmapEffects, usar transformaciones y establecer propiedades básicas de objetos.  
  
## <a name="see-also"></a>Vea también

- [Crear un botón mediante el uso de XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre efectos de imagen](../graphics-multimedia/bitmap-effects-overview.md)
