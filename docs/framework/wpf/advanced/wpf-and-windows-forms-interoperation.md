---
title: Interoperabilidad de WPF y Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187152"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperabilidad entre Windows Forms y WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]y Windows Forms presentan dos arquitecturas diferentes para crear interfaces de aplicación. El <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> espacio de nombres proporciona clases que habilitan escenarios de interoperación comunes. Las dos clases clave que <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost>implementan capacidades de interoperación son y . En este tema se describen los escenarios de interoperación que son compatibles y los que no lo son.  
  
> [!NOTE]
> Se presta especial atención al escenario de un *control híbrido*. Un control híbrido tiene un control de una tecnología anidada en un control de otra tecnología (también se denomina *interoperación anidada*). Un *control híbrido multinivel* tiene más de un nivel de anidamiento de control híbrido. Un ejemplo de una interoperación anidada de varios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] niveles es un control de formularios Windows Forms que contiene un control, que contiene otro control de formularios Windows Forms. Los controles híbridos multinivel no se admiten.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hospedar controles de Windows Forms en WPF  
 Se admiten los siguientes escenarios de interoperación cuando un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control hospeda un control de formularios Windows Forms:  
  
- El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control puede hospedar uno o varios controles de formularios Windows Forms mediante XAML.  
  
- Puede hospedar uno o varios controles de formularios Windows Forms mediante código.  
  
- Puede hospedar controles de contenedor de formularios Windows Forms que contienen otros controles de formularios Windows Forms.  
  
- Puede hospedar un formulario maestro/detalle con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] maestro y detalles de Windows Forms.  
  
- Puede hospedar un formulario maestro/detalle con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un maestro de Windows Forms y detalles.  
  
- Puede hospedar uno o más controles ActiveX.  
  
- Puede hospedar uno o varios controles compuestos.  
  
- Puede hospedar controles híbridos mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Puede hospedar controles híbridos mediante código.  
  
### <a name="layout-support"></a>Compatibilidad de diseño  
 En la lista siguiente se describen las limitaciones conocidas cuando el <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento intenta integrar su control hospedado de formularios Windows Forms en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de diseño.  
  
- En algunos casos, los controles de formularios Windows Forms no se pueden cambiar de tamaño o solo se pueden ajustar a dimensiones específicas. Por ejemplo, un <xref:System.Windows.Forms.ComboBox> control de formularios Windows Forms solo admite un único alto, que se define por el tamaño de fuente del control. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un diseño dinámico, que supone que los <xref:System.Windows.Forms.ComboBox> elementos pueden estirarse verticalmente, un control hospedado no se estirará como se esperaba.  
  
- Los controles de formularios Windows Forms no se pueden girar ni sesgar. Por ejemplo, al rotar la interfaz de usuario 90 grados, los controles hospedados de Formularios Windows Forms mantendrán su posición vertical.  
  
- En la mayoría de los casos, los controles de formularios Windows Forms no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende de qué tan bien cada control de formularios Windows Forms admite el escalado.  
  
- En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Un control hospedado de formularios Windows Forms se dibuja en un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND independiente, por lo que siempre se dibuja encima de los elementos.  
  
- Los controles de formularios Windows Forms admiten el escalado automático en función del tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propiedades ambientales de los controles tienen equivalentes de Formularios Windows Forms. Estas propiedades ambientales se propagan a los controles hospedados de Windows Forms y se exponen como propiedades públicas en el <xref:System.Windows.Forms.Integration.WindowsFormsHost> control. El <xref:System.Windows.Forms.Integration.WindowsFormsHost> control traduce [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cada propiedad ambiente en su equivalente de formularios Windows Forms.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------|---------------|-------------------|  
|Transparencia|La representación del control de formularios Windows Forms admite transparencia. El fondo del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control primario puede convertirse en el fondo de los controles hospedados de Windows Forms.|Algunos controles de formularios Windows Forms no admiten la transparencia. Por ejemplo, <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.ComboBox> los controles y no [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]serán transparentes cuando se hospedan en .|  
|Tabulación|El orden de tabulación para los controles hospedados de formularios Windows Forms es el mismo que cuando esos controles se hospedan en una aplicación basada en formularios Windows Forms.<br /><br /> La tabulación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de un control a un control de formularios Windows Forms con las teclas TAB y MAYÚS+TAB funciona como de costumbre.<br /><br /> Los controles de <xref:System.Windows.Forms.Control.TabStop%2A> formularios Windows `false` Forms que tienen un valor de propiedad de no reciben el foco cuando el usuario tabula los controles.<br /><br /> - <xref:System.Windows.Forms.Integration.WindowsFormsHost> Cada control <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> tiene un valor, <xref:System.Windows.Forms.Integration.WindowsFormsHost> que determina cuándo ese control recibirá el foco.<br />- Los controles de formularios <xref:System.Windows.Forms.Integration.WindowsFormsHost> Windows Forms que se <xref:System.Windows.Forms.Control.TabIndex%2A> encuentran dentro de un contenedor siguen el orden especificado por la propiedad. La tabulación desde el último índice de tabulación sitúa el foco en el siguiente control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en el caso de que haya alguno. Si no existe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ningún otro control enfocoso, la tabulación vuelve al primer control de formularios Windows Forms en el orden de tabulación.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>los valores de <xref:System.Windows.Forms.Integration.WindowsFormsHost> los controles dentro de los controles <xref:System.Windows.Forms.Integration.WindowsFormsHost> de windows Forms relacionados con el mismo nivel que se encuentran en el control.<br />- La tabulación respeta el comportamiento específico del control. Por ejemplo, al presionar <xref:System.Windows.Forms.TextBox> la tecla <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> TAB en `true` un control que tiene un valor de propiedad de entra una ficha en el cuadro de texto en lugar de mover el foco.|No aplicable.|  
|Navegación con las teclas de dirección|- Navegación con teclas <xref:System.Windows.Forms.Integration.WindowsFormsHost> de flecha en el control es la misma que en un control contenedor de formularios Windows Forms ordinario: las teclas FLECHA ARRIBA y FLECHA IZQUIERDA seleccionan el control anterior, y las teclas FLECHA ABAJO y FLECHA DERECHA seleccionan el siguiente control.<br />- Las teclas FLECHA ARRIBA y FLECHA IZQUIERDA del <xref:System.Windows.Forms.Integration.WindowsFormsHost> primer control contenido en el control realizan la misma acción que el método abreviado de teclado SHIFT+TAB. Si hay un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control enfocable, el foco se mueve fuera del <xref:System.Windows.Forms.Integration.WindowsFormsHost> control. Este comportamiento difiere del <xref:System.Windows.Forms.ContainerControl> comportamiento estándar en que no se produce ningún ajuste al último control. Si no existe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ningún otro control enfocoso, el foco vuelve al último control de formularios Windows Forms en el orden de tabulación.<br />- Las teclas FLECHA ABAJO y FLECHA DERECHA del <xref:System.Windows.Forms.Integration.WindowsFormsHost> último control contenido en el control realizan la misma acción que la tecla TAB. Si hay un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control enfocable, el foco se mueve fuera del <xref:System.Windows.Forms.Integration.WindowsFormsHost> control. Este comportamiento difiere del <xref:System.Windows.Forms.ContainerControl> comportamiento estándar en que no se produce ningún ajuste al primer control. Si no existe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ningún otro control enfocoso, el foco vuelve al primer control de formularios Windows Forms en el orden de tabulación.|No aplicable.|  
|Aceleradores|Los aceleradores funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|Los aceleradores duplicados entre tecnologías no funcionan como los aceleradores duplicados normales. Cuando un acelerador se duplica entre tecnologías, con al menos uno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un control de formularios Windows Forms y el otro en un control, el control de formularios Windows Forms siempre recibe el acelerador. El foco no alterna entre los controles cuando se presiona el acelerador duplicado.|  
|Teclas de método abreviado|Las teclas de método abreviado funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|- Las teclas de método abreviado de formularios Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms que se controlan en la fase de preprocesamiento siempre tienen prioridad sobre las teclas de método abreviado. Por ejemplo, si <xref:System.Windows.Forms.ToolStrip> tiene un control con las teclas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] método abreviado CTRL+S <xref:System.Windows.Forms.ToolStrip> definidas y hay un comando enlazado a CTRL+S, el controlador de control siempre se invoca primero, independientemente del foco.<br />- Las teclas de método abreviado <xref:System.Windows.Forms.Control.KeyDown> de formularios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Windows Forms controladas por el evento se procesan en último lugar en . Puede evitar este comportamiento reemplazando el método <xref:System.Windows.Forms.Control.IsInputKey%2A> del control <xref:System.Windows.Forms.Control.PreviewKeyDown> de formularios Windows Forms o controlando el evento. Devuelve `true` desde <xref:System.Windows.Forms.Control.IsInputKey%2A> el método o establece <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> el `true` valor <xref:System.Windows.Forms.Control.PreviewKeyDown> de la propiedad en el controlador de eventos.|  
|AcceptsReturn, AcceptsTab y otros comportamientos específicos del control|Las propiedades que cambian el comportamiento predeterminado del teclado funcionan como <xref:System.Windows.Forms.Control.IsInputKey%2A> de `true`costumbre, suponiendo que el control de formularios Windows Forms invalida el método que se va a devolver .|Los controles de formularios Windows Forms <xref:System.Windows.Forms.Control.KeyDown> que cambian el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comportamiento predeterminado del teclado controlando el evento se procesan en último lugar en el control host. Dado que estos controles se procesan en último lugar, pueden dar lugar a un comportamiento inesperado.|  
|Eventos Enter y Leave|Cuando el foco no <xref:System.Windows.Forms.Integration.ElementHost> va al control contenedor, los eventos Enter y Leave <xref:System.Windows.Forms.Integration.WindowsFormsHost> se generan como de costumbre cuando el foco cambia en un único control.|Los eventos Enter and Leave no se generan cuando se producen los siguientes cambios en el foco:<br /><br /> - De dentro <xref:System.Windows.Forms.Integration.WindowsFormsHost> a fuera de un control.<br />- Desde el <xref:System.Windows.Forms.Integration.WindowsFormsHost> exterior hasta el interior de un control.<br />- Fuera <xref:System.Windows.Forms.Integration.WindowsFormsHost> de un control.<br />- Desde un control de <xref:System.Windows.Forms.Integration.WindowsFormsHost> formularios <xref:System.Windows.Forms.Integration.ElementHost> Windows Forms hospedado <xref:System.Windows.Forms.Integration.WindowsFormsHost>en un control a un control hospedado dentro del mismo archivo .|  
|Subprocesamiento múltiple|Se admiten todas las variedades de multithreading.|Tanto los formularios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms como las tecnologías asumen un modelo de simultaneidad de subproceso único. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de asistencia funcionan correctamente cuando se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan para aplicaciones híbridas que contienen formularios Windows Forms y controles.|No aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entre formularios Windows Forms y controles.|No aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre formularios Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.|No aplicable.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hospedar controles de WPF en Windows Forms  
 Se admiten los siguientes escenarios de interoperación cuando un control de formularios Windows Forms hospeda un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control:  
  
- Hospedar uno o varios controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  
  
- Asociar una hoja de propiedades con uno o varios controles hospedados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar una o varias páginas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un formulario.  
  
- Iniciar una ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar un formulario maestro/detalle con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un maestro de Windows Forms y detalles.  
  
- Hospedar un formulario maestro/detalle con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] maestro y detalles de Windows Forms.  
  
- Hospedar controles personalizados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar controles híbridos.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las propiedades ambientales de los controles de formularios Windows Forms tienen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes. Estas propiedades ambientales se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] propagan a los controles <xref:System.Windows.Forms.Integration.ElementHost> hospedados y se exponen como propiedades públicas en el control. El <xref:System.Windows.Forms.Integration.ElementHost> control traduce cada propiedad ambiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de formularios Windows Forms a su equivalente.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------|---------------|-------------------|  
|Transparencia|La representación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite la transparencia. El fondo del control primario de formularios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms puede convertirse en el fondo de los controles hospedados.|No aplicable.|  
|Subprocesamiento múltiple|Se admiten todas las variedades de multithreading.|Tanto los formularios [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms como las tecnologías asumen un modelo de simultaneidad de subproceso único. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de asistencia funcionan correctamente cuando se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usan para aplicaciones híbridas que contienen formularios Windows Forms y controles.|No aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entre formularios Windows Forms y controles.|No aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre formularios Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controles.|No aplicable.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
