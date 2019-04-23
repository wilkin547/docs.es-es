---
title: 'Tutorial: Crear un botón mediante Microsoft Expression Blend'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
- converting [WPF], shape to button
- Expression Blend [WPF Designer]
ms.assetid: ff5037c2-bba7-4cae-8abb-6475b686c48e
ms.openlocfilehash: 3cf9d133aee5a2c3d93c1a464c96fdaebcf230f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300466"
---
# <a name="walkthrough-create-a-button-by-using-microsoft-expression-blend"></a>Tutorial: Crear un botón mediante Microsoft Expression Blend
Este tutorial le guía a través del proceso de creación de un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] botón personalizado mediante Microsoft Expression Blend.  
  
> [!IMPORTANT]
>  Microsoft Expression Blend funciona generando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que, a continuación, se compila para crear el programa ejecutable. Si prefiere trabajar con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] directamente, hay otro tutorial que crea la misma aplicación como uno con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] con Visual Studio, en lugar de Blend. Consulte [crear un botón mediante el uso de XAML](walkthrough-create-a-button-by-using-xaml.md) para obtener más información.  
  
 La siguiente ilustración muestra el botón personalizado que va a crear.  
  
 ![Botón personalizado que va a crear](./media/custom-button-blend-intro.jpg "custom_button_blend_Intro")  
  
## <a name="convert-a-shape-to-a-button"></a>Convertir una forma en un botón  
 En la primera parte de este tutorial se crea la apariencia del botón personalizado personalizada. Para ello, primero convierta un rectángulo a un botón. Agregar, a continuación, formas adicionales a la plantilla del botón, crear un botón con un aspecto más complejo. ¿Por qué no comenzar con un botón normal y personalizarlo? Dado que un botón tiene una funcionalidad integrada que no es necesario; para los botones personalizados, es más fácil empezar con un rectángulo.  
  
#### <a name="to-create-a-new-project-in-expression-blend"></a>Para crear un nuevo proyecto en Expression Blend  
  
1. Inicie Expression Blend. (Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft Expression**y, a continuación, haga clic en **Microsoft Expression Blend**.)  
  
2. Maximice la aplicación si es necesario.  
  
3. En el menú **Archivo**, haga clic en **Nuevo proyecto**.  
  
4. Seleccione **aplicación estándar (.exe)**.  
  
5. Denomine el proyecto `CustomButton` y presione **Aceptar**.  
  
 En este momento tiene un espacio en blanco [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] proyecto. Puede presionar F5 para ejecutar la aplicación. Como cabría esperar, la aplicación consta de sólo una ventana en blanco. A continuación, crear un rectángulo redondeado y convertirlo en un botón.  
  
#### <a name="to-convert-a-rectangle-to-a-button"></a>Para convertir un rectángulo en un botón  
  
1. **Establezca la propiedad de la ventana en segundo plano en negro:** Seleccione la ventana, haga clic en el **ficha propiedades**y establezca el <xref:System.Windows.Controls.Control.Background%2A> propiedad `Black`.  
  
     ![Cómo establecer el fondo de un botón en negro](./media/custom-button-blend-changebackground.png "custom_button_blend_ChangeBackground")  
  
2. **Dibuja un rectángulo aproximadamente del tamaño de un botón en la ventana:** Seleccione la herramienta rectángulo en el panel de herramientas izquierda y arrastre el rectángulo a la ventana.  
  
     ![Cómo dibujar un rectángulo](./media/custom-button-blend-drawrect.png "custom_button_blend_DrawRect")  
  
3. **Redondear las esquinas del rectángulo:** Arrastre los puntos de control del rectángulo o establecer directamente la <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades. Establezca los valores de <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> a 20.  
  
     ![Realización de las esquinas de un rectángulo redondeado](./media/custom-button-blend-roundcorners.png "custom_button_blend_RoundCorners")  
  
4. **Cambie el rectángulo en un botón:** Seleccione el rectángulo. En el **herramientas** menú, haga clic en **Crear botón**.  
  
     ![Cómo convertir una forma en un botón](./media/custom-button-blend-makebutton.png "custom_button_blend_MakeButton")  
  
5. **Especificar el ámbito de la plantilla de estilo:** Aparece un cuadro de diálogo similar al siguiente.  
  
     ![El cuadro de diálogo "Create Style Resource"](./media/custom-button-blend-makebutton2.gif "custom_button_blend_MakeButton2")  
  
     Para **nombre de recurso (clave)**, seleccione **aplicar a todo**.  Esto hará que la plantilla de botón se aplican a todos los objetos que están los botones y el estilo resultante. Para **definir en**, seleccione **aplicación**. Esto hará que el estilo resultante y la plantilla de botón tienen ámbito a través de toda la aplicación. Al establecer los valores de estos dos cuadros, el estilo de botón y la plantilla se aplican a todos los botones dentro de toda la aplicación y cualquier botón que cree en la aplicación utilizará, de forma predeterminada, esta plantilla.  
  
## <a name="edit-the-button-template"></a>Editar la plantilla de botón  
 Ahora dispone de un rectángulo que se ha cambiado a un botón. En esta sección, modificará la plantilla del botón y personalizar aún más su aspecto.  
  
#### <a name="to-edit-the-button-template-to-change-the-button-appearance"></a>Para editar la plantilla de botón para cambiar la apariencia del botón  
  
1. **Vaya a la vista de la plantilla de edición:** Para personalizar aún más el aspecto de nuestro botón, se debe editar la plantilla de botón. Esta plantilla se creó al convertir el rectángulo en un botón. Para editar la plantilla de botón, haga clic en el botón y seleccione **Editar partes del Control (plantilla)** y, a continuación, **Editar plantilla**.  
  
     ![Cómo editar una plantilla](./media/custom-button-blend-edittemplate.jpg "custom_button_blend_EditTemplate")  
  
     En el editor de plantillas, tenga en cuenta que el botón se divide ahora en un <xref:System.Windows.Shapes.Rectangle> y <xref:System.Windows.Controls.ContentPresenter>. El <xref:System.Windows.Controls.ContentPresenter> se utiliza para presentar el contenido del botón (por ejemplo, la cadena "Button"). Tanto el rectángulo y <xref:System.Windows.Controls.ContentPresenter> se colocan dentro de un <xref:System.Windows.Controls.Grid>.  
  
     ![Componentes de la presentación de un rectángulo](./media/custom-button-blend-templatepanel.png "custom_button_blend_TemplatePanel")  
  
2. **Cambiar los nombres de los componentes de plantilla:** Haga clic en el rectángulo en el inventario de la plantilla, cambiar el <xref:System.Windows.Shapes.Rectangle> asigne un nombre de "[rectángulo]" a "RectánguloExterior" y cambie "[ContentPresenter]" a "MiContentPresenter".  
  
     ![Cómo cambiar el nombre de un componente de una plantilla](./media/custom-button-blend-renamecomponents.png "custom_button_blend_RenameComponents")  
  
3. **Modificar el rectángulo que está vacía en (por ejemplo, un anillo):** Seleccione **RectánguloExterior** y establecer <xref:System.Windows.Shapes.Shape.Fill%2A> en "Transparent" y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> a 5.  
  
     ![Cómo crear un rectángulo vacío](./media/custom-button-blend-changerectproperties.png "custom_button_blend_ChangeRectProperties")  
  
     A continuación, establezca el <xref:System.Windows.Shapes.Shape.Stroke%2A> el color de todo lo que será la plantilla. Para ello, haga clic en el pequeño cuadro en blanco junto al **trazo**, seleccione **expresión personalizada**y escriba "{TemplateBinding Background}" en el cuadro de diálogo.  
  
     ![Cómo establecer el uso del color de la plantilla](./media/custom-button-blend-templatestroke.png "custom_button_blend_TemplateStroke")  
  
4. **Crear un rectángulo interno:** Ahora, cree otro rectángulo (asígnele el nombre "RectánguloInterior") y colóquela simétricamente en el interior de **RectánguloExterior** . Para este tipo de trabajo, probablemente deseará hacer zoom para aumentar el tamaño del botón en el área de edición.  
  
    > [!NOTE]
    >  El rectángulo podría ser diferente de la que se muestra en la figura (por ejemplo, es posible que tenga esquinas redondeadas).  
  
     ![Cómo crear un rectángulo dentro de otro](./media/custom-button-blend-innerrectangleproperties.png "custom_button_blend_innerRectangleProperties")  
  
5. **Mover ContentPresenter en la parte superior:** En este momento, es posible que el texto "Button" no será visible más largo. Si es así, esto es porque **RectánguloInterior** está en la parte superior de la **MiContentPresenter**. Para solucionar este problema, arrastre **MiContentPresenter** debajo **RectánguloInterior**. Cambiar la posición de los rectángulos y **MiContentPresenter** para un aspecto parecido al siguiente.  
  
    > [!NOTE]
    >  Como alternativa, también puede colocar **MiContentPresenter** en la parte superior, haga clic en él y presione **Enviar hacia delante**.  
  
     ![Cómo mover un botón encima de otro botón](./media/custom-button-blend-innerrectangle2.png "custom_button_blend_innerRectangle2")  
  
6. **Cambiar el aspecto de RectánguloInterior:** Establecer el <xref:System.Windows.Shapes.Rectangle.RadiusX%2A>, <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>, y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> valores a 20. Static solo puede, establezca el <xref:System.Windows.Shapes.Shape.Fill%2A> al fondo de la plantilla mediante la expresión personalizada "{TemplateBinding Background}") y establezca <xref:System.Windows.Shapes.Shape.Stroke%2A> a "transparent". Tenga en cuenta que la configuración de la <xref:System.Windows.Shapes.Shape.Fill%2A> y <xref:System.Windows.Shapes.Shape.Stroke%2A> de **RectánguloInterior** son lo opuesto de aquellos **RectánguloExterior**.  
  
     ![Cómo cambiar la apariencia de un rectángulo](./media/custom-button-blend-glassrectangleproperties1.png "custom_button_blend_glassRectangleProperties1")  
  
7. **Agregar una capa de cristal en la parte superior:** Es la última pieza de personalizar la apariencia del botón Agregar una capa de cristal en la parte superior. Esta capa de cristal consta de un tercer rectángulo. Dado que el cristal cubrirá todo el botón, el rectángulo de cristal es similar en dimensiones para la **RectánguloExterior**. Por lo tanto, crear el rectángulo basta con realizar una copia de la **RectánguloExterior**. Resaltar **RectánguloExterior** y use CTRL+C y CTRL+V para realizar una copia. Nombre de este nuevo rectángulo "glassCube".  
  
8. **Cambiar la posición de glassCube si es necesario:** Si **glassCube** es ya no coloca de modo que cubra todo el botón, arrástrela hasta su posición.  
  
9. **Ofrecen una forma ligeramente diferente que RectánguloExterior de glassCube:** Cambiar las propiedades de **glassCube**. Empezar cambiando el <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> propiedades a 10 y el <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> a 2.  
  
     ![Configuración de la apariencia de glassCube](./media/custom-button-blend-glasscubeappearance.gif "custom_button_blend_GlassCubeAppearance")  
  
10. **Asegúrese de glassCube el aspecto de cristal:** Establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> para ello consulte mediante el uso de un degradado lineal que es el 75% opaco y alterna entre el color negro y transparente durante 6 aproximadamente uniformemente espaciados intervalos. Esto es lo que se debe establecer los delimitadores de degradado:  
  
    -   Delimitador de degradado 1: En blanco con el valor alfa del 75%  
  
    -   Delimitador de degradado 2: Transparente  
  
    -   Delimitador de degradado 3: En blanco con el valor alfa del 75%  
  
    -   Delimitador de degradado 4: Transparente  
  
    -   Delimitador de degradado 5: En blanco con el valor alfa del 75%  
  
    -   Delimitador de degradado 6: Transparente  
  
     Esto crea un aspecto de cristal "ondulado".  
  
     ![Un rectángulo que es similar a vidrio](./media/custom-button-blend-glassrectangleproperties2.png "custom_button_blend_glassRectangleProperties2")  
  
11. **Ocultar la capa de cristal:** Ahora que puede ver el aspecto de la capa de ello, vaya a la **panel apariencia** de la **panel Propiedades** y establece la opacidad en 0% para ocultarlo. En las secciones siguientes, usaremos eventos y desencadenadores de propiedad para mostrar y manipular la capa de cristal.  
  
     ![Cómo ocultar el rectángulo de cristal](./media/custom-button-glassrectangleproperties3.gif "custom_button_glassRectangleProperties3")  
  
## <a name="customize-the-button-behavior"></a>Personalizar el comportamiento del botón  
 En este momento, ha personalizado la presentación del botón editando su plantilla, pero el botón no reacciona a las acciones del usuario como botones típico (por ejemplo, cambiando su aspecto al pasar el mouse sobre, recibe el foco y haga clic en.) Los dos procedimientos siguientes muestran cómo compilar comportamientos como estas en el botón personalizado. Empezamos a con desencadenadores de propiedad simples y, a continuación, agregue las animaciones y desencadenadores de eventos.  
  
#### <a name="to-set-property-triggers"></a>Para establecer la propiedad triggers  
  
1. **Crear un nuevo desencadenador de propiedad:** Con **glassCube** seleccionado, haga clic en **+ propiedad** en el **desencadenadores** panel (consulte la figura siguiente en el paso siguiente). Esto crea un desencadenador de propiedad con un desencadenador de propiedad predeterminado.  
  
2. **Asegúrese de IsMouseOver la propiedad utilizada por el desencadenador:** Cambie la propiedad a <xref:System.Windows.UIElement.IsMouseOver%2A>. Esto hace que el desencadenador de propiedad activar cuando la <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad es `true` (cuando el usuario elige el botón con el mouse).  
  
     ![Cómo establecer un desencadenador en una propiedad](./media/custom-button-blend-ismousedoverpropertytrigger.png "custom_button_blend_IsMousedOverPropertyTrigger")  
  
3. **IsMouseOver desencadena la opacidad del 100% de glassCube:** Tenga en cuenta que el **grabación de desencadenadores que se encuentra en** (consulte la ilustración anterior). Esto significa que cualquier cambio que realice en los valores de propiedad **glassCube** mientras se está grabando en se convertirá en una acción que se lleva a cabo cuando <xref:System.Windows.UIElement.IsMouseOver%2A> es `true`. Durante la grabación, cambie el <xref:System.Windows.UIElement.Opacity%2A> de **glassCube** al 100%.  
  
     ![Cómo establecer la opacidad de un botón](./media/custom-button-blend-ismousedoverpropertytrigger2.gif "custom_button_blend_IsMousedOverPropertyTrigger2")  
  
     Ahora ha creado su primer desencadenador de propiedad. Tenga en cuenta que el **panel desencadenadores** del editor ha grabado el <xref:System.Windows.UIElement.Opacity%2A> se cambia al 100%.  
  
     ![El panel "Desencadenadores"](./media/custom-button-blend-propertytriggerinfo.png "custom_button_blend_PropertyTriggerInfo")  
  
     Presione F5 para ejecutar la aplicación y mueva el puntero sobre y el botón de cierre. Debería ver que la capa de cristal aparecen al pasar el mouse sobre el botón y desaparecen cuando el puntero sale.  
  
4. **Cambio del valor de trazo IsMouseOver desencadenadores:** Vamos a asociar algunas otras acciones con el <xref:System.Windows.UIElement.IsMouseOver%2A> desencadenador. Mientras continúa la grabación, cambie la selección de **glassCube** a **RectánguloExterior**. A continuación, establezca el <xref:System.Windows.Shapes.Shape.Stroke%2A> de **RectánguloExterior** a la expresión personalizada "{DynamicResource {x: Static SystemColors.HighlightBrushKey}}". Esto establece la <xref:System.Windows.Shapes.Shape.Stroke%2A> a típica resaltar el color utilizado por los botones. Presione F5 para ver el efecto cuando desplaza el mouse sobre el botón.  
  
     ![Cómo establecer el trazo en el color de resaltado](./media/custom-button-blend-ismousedoverpropertytrigger3.png "custom_button_blend_IsMousedOverPropertyTrigger3")  
  
5. **IsMouseOver desencadena texto borroso:** Vamos a asociar una acción más a la <xref:System.Windows.UIElement.IsMouseOver%2A> desencadenador de propiedad. Poner el contenido del botón se ve borroso un poco cuando el cristal aparece encima de él. Para ello, podemos aplicar un desenfoque <xref:System.Windows.Media.Effects.BitmapEffect> a la <xref:System.Windows.Controls.ContentPresenter> (**MiContentPresenter**).  
  
     ![Cómo difuminar el contenido de un botón](./media/custom-button-blend-propertytriggerwithbitmapeffect.png "custom_button_blend_PropertyTriggerWithBitMapEffect")  
  
    > [!NOTE]
    >  Para devolver el **panel Propiedades** a lo que estaba antes de que la búsqueda de <xref:System.Windows.Media.Effects.BitmapEffect>, borre el texto de la **cuadro de búsqueda**.  
  
     En este momento, hemos usado un desencadenador de propiedad con varias acciones asociadas para crear el comportamiento de resaltado cuando el puntero del mouse entra y sale del área del botón. Es otro comportamiento típico de un botón Resaltar cuando tiene el foco (como cuando se hace clic). Podemos agregar dicho comportamiento agregando otro desencadenador de propiedad para el <xref:System.Windows.UIElement.IsFocused%2A> propiedad.  
  
6. **Crear desencadenador de propiedad para IsFocused:** Con el mismo procedimiento que para <xref:System.Windows.UIElement.IsMouseOver%2A> (consulte el primer paso de esta sección), cree otro desencadenador de propiedad para el <xref:System.Windows.UIElement.IsFocused%2A> propiedad. Mientras **grabación de desencadenadores que se encuentra en**, agregue las siguientes acciones para el desencadenador:  
  
    -   **glassCube** Obtiene un <xref:System.Windows.UIElement.Opacity%2A> del 100%.  
  
    -   **RectánguloExterior** Obtiene un <xref:System.Windows.Shapes.Shape.Stroke%2A> valor de expresión personalizada "{DynamicResource {x: Static SystemColors.HighlightBrushKey}}".  
  
 Como último paso en este tutorial, agregaremos las animaciones en el botón. Estas animaciones se desencadena por eventos, en concreto, el <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
#### <a name="to-use-event-triggers-and-animations-to-add-interactivity"></a>Para usar animaciones y desencadenadores de eventos para agregar interactividad  
  
1. **Crear un desencadenador de evento MouseEnter:** Agregue un nuevo desencadenador de eventos y seleccione <xref:System.Windows.UIElement.MouseEnter> como el evento que usa en el desencadenador.  
  
     ![Cómo crear un desencadenador de eventos MouseEnter](./media/custom-button-blend-mouseovereventtrigger.png "custom_button_blend_MouseOverEventTrigger")  
  
2. **Crear una escala de tiempo de animación:** A continuación, asociar una escala de tiempo de animación para el <xref:System.Windows.UIElement.MouseEnter> eventos.  
  
     ![Cómo agregar una escala de tiempo de animación a un evento](./media/custom-button-blend-mouseovereventtrigger2.png "custom_button_blend_MouseOverEventTrigger2")  
  
     Después de presionar **Aceptar** para crear una nueva escala de tiempo, un **Panel de escala de tiempo** aparece y está visible en el panel de diseño "Escala de tiempo de grabación está activada". Esto significa que podemos empezar a registrar los cambios de propiedad en la escala de tiempo (animar cambios de propiedades).  
  
    > [!NOTE]
    >  Es posible que deba cambiar el tamaño de la ventana o los paneles para ver la pantalla.  
  
     ![El panel de escala de tiempo](./media/custom-button-blend-mouseovereventtrigger3.png "custom_button_blend_MouseOverEventTrigger3")  
  
3. **Crear un fotograma clave:** Para crear una animación, seleccione el objeto que desea animar, cree dos o más fotogramas en la escala de tiempo y para los fotogramas clave, establezca los valores de propiedad que desea que la animación para interpolar entre. La figura siguiente le guiará por la creación de un fotograma clave.  
  
     ![Cómo crear un fotograma clave](./media/custom-button-blend-mouseovereventtrigger4.png "custom_button_blend_MouseOverEventTrigger4")  
  
4. **Reducir glassCube en este fotograma clave:** Con el segundo fotograma clave seleccionado, reducir el tamaño de la **glassCube** al 90% de su tamaño completo mediante la **tamaño transformar**.  
  
     ![Cómo reducir el tamaño de un botón](./media/custom-button-blend-sizetransform.png "custom_button_blend_SizeTransform")  
  
     Presione F5 para ejecutar la aplicación. Mueva el puntero del mouse sobre el botón. Tenga en cuenta que la capa de cristal se reduce en el botón de la parte superior.  
  
5. **Cree otro desencadenador de evento y asociar una animación diferentes:** Vamos a agregar una animación más. Utilice un procedimiento similar a lo que usó para crear la animación anterior de desencadenador de evento:  
  
    1.  Crear un nuevo evento desencadenador mediante el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
    2.  Asociar una nueva escala de tiempo con el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  
  
     ![Cómo crear una nueva escala de tiempo](./media/custom-button-blend-clickeventtrigger1.png "custom_button_blend_ClickEventTrigger1")  
  
    1.  Para esta escala de tiempo, cree dos fotogramas clave, en segundos entre 0,0 y el otro a 0,3 segundos.  
  
    2.  Con el fotograma clave en 0,3 segundos resaltado, establezca el **ángulo de giro** a 360 grados.  
  
     ![Cómo crear una transformación de giro](./media/custom-button-blend-rotatetransform.gif "custom_button_blend_RotateTransform")  
  
    1.  Presione F5 para ejecutar la aplicación. Haga clic en el botón. Tenga en cuenta que la capa de cristal gira en torno a.  
  
## <a name="conclusion"></a>Conclusión  
 Ha completado un botón personalizado. Hizo este con una plantilla de botón que se aplica a todos los botones de la aplicación. Si deja el modo de edición de plantillas (consulte la figura siguiente) y crea más botones, verá que su apariencia y comportamiento como el botón personalizado en lugar de como el botón predeterminado.  
  
 ![La plantilla de botón personalizado](./media/custom-button-blend-scopeup.gif "custom_button_blend_ScopeUp")  
  
 ![Varios botones que usan la misma plantilla](./media/custom-button-blend-createmultiplebuttons.png "custom_button_blend_CreateMultipleButtons")  
  
 Presione F5 para ejecutar la aplicación. Haga clic en los botones y observe cómo todos ellos comportan del mismo.  
  
 Recuerde que mientras estaba personalizando la plantilla, establezca el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de **RectánguloInterior** y <xref:System.Windows.Shapes.Shape.Stroke%2A> propiedad **RectánguloExterior** para el fondo de la plantilla ({} Fondo de TemplateBinding}). Por este motivo, cuando se establece el color de fondo de los botones individuales, se utilizará el fondo que se establece para las propiedades respectivas. Pruebe a cambiar los fondos ahora. En la ilustración siguiente, se utilizan degradados diferentes. Por lo tanto, aunque una plantilla es útil para personalización general de controles como los botones, controles basados en plantillas aún pueden modificarse para que sean distintos entre sí.  
  
 ![Botones con la misma plantilla que tienen un aspecto diferente](./media/custom-button-blend-blendconclusion.jpg "custom_button_blend_BlendConclusion")  
  
 En conclusión, en el proceso de personalización de una plantilla de botón ha aprendido a hacer lo siguiente en Microsoft Expression Blend:  
  
-   Personalizar la apariencia de un control.  
  
-   Establecer desencadenadores de propiedad. Desencadenadores de propiedad resultan muy útiles, ya que pueden usarse en la mayoría de los objetos, no sólo en los controles.  
  
-   Establecer los desencadenadores de eventos. Desencadenadores de eventos son muy útiles porque se puede usar en la mayoría de los objetos, no sólo en los controles.  
  
-   Crear animaciones.  
  
-   Varios: crear degradados, agregar BitmapEffects, utilizar las transformaciones y establecer las propiedades básicas de objetos.  
  
## <a name="see-also"></a>Vea también

- [Crear un botón mediante el uso de XAML](walkthrough-create-a-button-by-using-xaml.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
- [Información general sobre el dibujo con colores sólidos y degradados](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Información general sobre efectos de imagen](../graphics-multimedia/bitmap-effects-overview.md)
