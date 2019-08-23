---
title: Interoperabilidad entre Windows Forms y WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 0326f283cb271d1578e94b648e423c6f88c579f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917402"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperabilidad entre Windows Forms y WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] presentan dos arquitecturas diferentes para crear interfaces de aplicaciones. El <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> espacio de nombres proporciona clases que habilitan escenarios comunes de interoperación. Las dos clases clave que implementan las capacidades de <xref:System.Windows.Forms.Integration.WindowsFormsHost> interoperación son y <xref:System.Windows.Forms.Integration.ElementHost>. En este tema se describen los escenarios de interoperación que son compatibles y los que no lo son.  
  
> [!NOTE]
> Se presta especial atención al escenario de un *control híbrido*. Un control híbrido tiene un control de una tecnología anidada en un control de otra tecnología (también se denomina *interoperación anidada*). Un *control híbrido multinivel* tiene más de un nivel de anidamiento de control híbrido. Un ejemplo de una interoperación anidada multinivel sería un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que contiene un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que contiene otro control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Los controles híbridos multinivel no se admiten.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hospedar controles de Windows Forms en WPF  
 Se admiten los siguientes escenarios de interoperación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando un control hospeda un control Windows Forms:  
  
- El control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede hospedar uno o varios controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mediante XAML.  
  
- Puede hospedar uno o varios controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mediante código.  
  
- Puede hospedar controles contenedores de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que contengan otros controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Puede hospedar un formulario principal/detalle con un formulario principal de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y un formulario de detalle de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Puede hospedar un formulario principal/detalle con un formulario principal de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y un formulario de detalle de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Puede hospedar uno o varios controles ActiveX.  
  
- Puede hospedar uno o varios controles compuestos.  
  
- Puede hospedar controles híbridos mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Puede hospedar controles híbridos mediante código.  
  
### <a name="layout-support"></a>Compatibilidad de diseño  
 En la lista siguiente se describen las limitaciones conocidas <xref:System.Windows.Forms.Integration.WindowsFormsHost> cuando el elemento intenta integrar su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en el sistema de diseño.  
  
- En algunos casos no se puede cambiar el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] (o solo se pueden fijar unas dimensiones específicas). Por ejemplo, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> control solo admite un alto, que se define mediante el tamaño de fuente del control. En un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diseño dinámico, que supone que los elementos se pueden expandir verticalmente, <xref:System.Windows.Forms.ComboBox> un control hospedado no se ajustará según lo esperado.  
  
- Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se pueden girar ni sesgar. Por ejemplo, al girar la interfaz de usuario 90 grados, los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mantendrán su posición vertical.  
  
- En la mayoría de los casos, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende del grado de compatibilidad del escalado de cada control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se dibujan en un HWND independiente, por lo que siempre se dibujan en la parte superior de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admiten el escalado automático en función del tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las propiedades ambiente de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen sus equivalentes en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Estas propiedades de ambiente se propagan a los controles [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados y se exponen como <xref:System.Windows.Forms.Integration.WindowsFormsHost> propiedades públicas en el control. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> control convierte cada [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedad de ambiente en su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalente.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------|---------------|-------------------|  
|Transparencia|La representación de controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admite la transparencia. El fondo del control primario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede convertir en el fondo de los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].|Algunos controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten la transparencia. Por ejemplo, los <xref:System.Windows.Forms.TextBox> controles <xref:System.Windows.Forms.ComboBox> y no serán transparentes cuando se hospeden en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Tabulación|El orden de tabulación de los controles hospedados de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] es el mismo que cuando dichos controles se hospedan en una aplicación basada en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> La tabulación desde un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con la tecla TAB y las teclas MAYÚS + TAB funciona como de costumbre.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]los controles que tienen <xref:System.Windows.Forms.Control.TabStop%2A> un valor de `false` propiedad de no reciben el foco cuando el usuario se desplaza por los controles.<br /><br /> -Cada <xref:System.Windows.Forms.Integration.WindowsFormsHost> control tiene un <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> valor <xref:System.Windows.Forms.Integration.WindowsFormsHost> , que determina Cuándo recibirá el foco.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]los controles incluidos en un <xref:System.Windows.Forms.Integration.WindowsFormsHost> contenedor siguen el orden especificado por la <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad. La tabulación desde el último índice de tabulación sitúa el foco en el siguiente control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en el caso de que haya alguno. Si no hay más controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puedan recibir el foco, la tabulación vuelve al primer control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en el orden de tabulación.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>los valores de los controles <xref:System.Windows.Forms.Integration.WindowsFormsHost> dentro de son relativos [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a los controles relacionados contenidos en <xref:System.Windows.Forms.Integration.WindowsFormsHost> el control.<br />- La tabulación respeta el comportamiento específico del control. Por ejemplo, al presionar la tecla TAB en <xref:System.Windows.Forms.TextBox> un control que tiene <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> un valor de `true` propiedad de, se escribe una tabulación en el cuadro de texto en lugar de mover el foco.|No aplicable.|  
|Navegación con las teclas de dirección|-La navegación con las teclas de <xref:System.Windows.Forms.Integration.WindowsFormsHost> dirección en el control es igual que en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] un control contenedor normal: Las teclas flecha arriba y flecha izquierda seleccionan el control anterior, y las teclas de flecha abajo y flecha derecha seleccionan el control siguiente.<br />-Las teclas flecha arriba y flecha izquierda del primer control contenido en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control realizan la misma acción que el método abreviado de teclado Mayús + Tab. Si hay un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control que pueda recibir el foco, el foco <xref:System.Windows.Forms.Integration.WindowsFormsHost> se mueve fuera del control. Este comportamiento difiere del comportamiento estándar <xref:System.Windows.Forms.ContainerControl> en que no se produce ningún ajuste en el último control. Si no hay más controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puedan recibir el foco, el foco vuelve al último control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en el orden de tabulación.<br />-Las teclas de flecha abajo y derecha del último control contenido en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control realizan la misma acción que la tecla TAB. Si hay un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control que pueda recibir el foco, el foco <xref:System.Windows.Forms.Integration.WindowsFormsHost> se mueve fuera del control. Este comportamiento difiere del comportamiento estándar <xref:System.Windows.Forms.ContainerControl> en que no se produce ningún ajuste en el primer control. Si no hay más controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puedan recibir el foco, el foco vuelve al primer control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en el orden de tabulación.|No aplicable.|  
|Aceleradores|Los aceleradores funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|Los aceleradores duplicados entre tecnologías no funcionan como los aceleradores duplicados normales. Cuando se duplica un acelerador entre tecnologías, con al menos uno de ellos en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y otro en un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] siempre recibe el acelerador. El foco no alterna entre los controles cuando se presiona el acelerador duplicado.|  
|Teclas de método abreviado|Las teclas de método abreviado funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|Las teclas de método abreviado de -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que se controlan en la fase de preprocesamiento siempre tienen prioridad sobre las teclas de método abreviado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, si tiene un <xref:System.Windows.Forms.ToolStrip> control con teclas de método abreviado CTRL + s definidos y hay un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comando enlazado a Ctrl + s, siempre se invoca primero el <xref:System.Windows.Forms.ToolStrip> controlador de control, independientemente del foco.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]las teclas de método abreviado que <xref:System.Windows.Forms.Control.KeyDown> controla el evento se procesan en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]último lugar. Puede evitar este comportamiento invalidando el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] método del <xref:System.Windows.Forms.Control.IsInputKey%2A> control o controlando el <xref:System.Windows.Forms.Control.PreviewKeyDown> evento. Vuelva `true` <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Control.PreviewKeyDown> del método o establezca el`true` valor de la propiedad en en el controlador de eventos. <xref:System.Windows.Forms.Control.IsInputKey%2A>|  
|AcceptsReturn, AcceptsTab y otros comportamientos específicos del control|Las propiedades que cambian el comportamiento predeterminado del teclado funcionan como de costumbre, suponiendo que el [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invalida el <xref:System.Windows.Forms.Control.IsInputKey%2A> método que `true`se va a devolver.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]los controles que cambian el comportamiento predeterminado del teclado <xref:System.Windows.Forms.Control.KeyDown> mediante el control del evento se procesan en último lugar en el control host. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dado que estos controles se procesan en último lugar, pueden dar lugar a un comportamiento inesperado.|  
|Eventos Enter y Leave|Cuando el foco no va al control contenedor <xref:System.Windows.Forms.Integration.ElementHost> , los eventos Enter y Leave se generan como de costumbre cuando el foco cambia en un <xref:System.Windows.Forms.Integration.WindowsFormsHost> solo control.|Los eventos Enter and Leave no se generan cuando se producen los siguientes cambios en el foco:<br /><br /> -Desde dentro a fuera de <xref:System.Windows.Forms.Integration.WindowsFormsHost> un control.<br />-Desde fuera hacia dentro de <xref:System.Windows.Forms.Integration.WindowsFormsHost> un control.<br />-Fuera de <xref:System.Windows.Forms.Integration.WindowsFormsHost> un control.<br />-Desde un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control hospedado en <xref:System.Windows.Forms.Integration.WindowsFormsHost> un control a <xref:System.Windows.Forms.Integration.ElementHost> un control hospedado dentro <xref:System.Windows.Forms.Integration.WindowsFormsHost>del mismo.|  
|Multithreading|Se admiten todas las variedades de multithreading.|Tanto la tecnología [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como la tecnología [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuponen que existe un modelo de simultaneidad de un solo subproceso. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de asistencia funcionan correctamente cuando se usan para aplicaciones híbridas que contienen los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hospedar controles de WPF en Windows Forms  
 Se admiten los siguientes escenarios de interoperación cuando un control Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospeda un control:  
  
- Hospedar uno o varios controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  
  
- Asociar una hoja de propiedades con uno o varios controles hospedados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar una o varias páginas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un formulario.  
  
- Iniciar una ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar un formulario principal/detalle con un formulario principal de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y un formulario de detalle de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar un formulario principal/detalle con un formulario principal de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y un formulario de detalle de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Hospedar controles personalizados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar controles híbridos.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las propiedades ambiente de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen sus equivalentes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Estas propiedades de ambiente se propagan a los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados y se exponen como <xref:System.Windows.Forms.Integration.ElementHost> propiedades públicas en el control. El <xref:System.Windows.Forms.Integration.ElementHost> control convierte cada [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] propiedad de ambiente en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalente.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------|---------------|-------------------|  
|Transparencia|La representación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite la transparencia. El fondo del control primario de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se puede convertir en el fondo de los controles hospedados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
|Multithreading|Se admiten todas las variedades de multithreading.|Tanto la tecnología [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] como la tecnología [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuponen que existe un modelo de simultaneidad de un solo subproceso. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de asistencia funcionan correctamente cuando se usan para aplicaciones híbridas que contienen los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No aplicable.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
