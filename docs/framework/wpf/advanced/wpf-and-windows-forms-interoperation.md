---
title: WPF y Windows Forms Interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 5141b84ecd002d920f0d4130bdc2529c0fce4994
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794052"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperabilidad entre Windows Forms y WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y Windows Forms presentan dos arquitecturas diferentes para crear interfaces de aplicación. El espacio de nombres <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> proporciona clases que habilitan escenarios comunes de interoperación. Las dos clases clave que implementan las capacidades de interoperación son <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>. En este tema se describen los escenarios de interoperación que son compatibles y los que no lo son.  
  
> [!NOTE]
> Se presta especial atención al escenario de un *control híbrido*. Un control híbrido tiene un control de una tecnología anidada en un control de otra tecnología (también se denomina *interoperación anidada*). Un *control híbrido multinivel* tiene más de un nivel de anidamiento de control híbrido. Un ejemplo de una interoperación anidada multinivel es un control Windows Forms que contiene un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que contiene otro control Windows Forms. Los controles híbridos multinivel no se admiten.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hospedar controles de Windows Forms en WPF  
 Se admiten los siguientes escenarios de interoperación cuando un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospeda un control Windows Forms:  
  
- El control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede hospedar uno o varios controles Windows Forms mediante XAML.  
  
- Puede hospedar uno o varios controles de Windows Forms mediante código.  
  
- Puede hospedar Windows Forms controles de contenedor que contienen otros controles de Windows Forms.  
  
- Puede hospedar un formulario principal/detalle con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] maestro y detalles de Windows Forms.  
  
- Puede hospedar un formulario principal/detalle con un Windows Forms maestro y detalles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Puede hospedar uno o varios controles ActiveX.  
  
- Puede hospedar uno o varios controles compuestos.  
  
- Puede hospedar controles híbridos mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Puede hospedar controles híbridos mediante código.  
  
### <a name="layout-support"></a>Compatibilidad de diseño  
 En la lista siguiente se describen las limitaciones conocidas cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta integrar su control de Windows Forms hospedado en el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- En algunos casos, no se puede cambiar el tamaño de los controles de Windows Forms o solo se puede ajustar a dimensiones específicas. Por ejemplo, un control de <xref:System.Windows.Forms.ComboBox> de Windows Forms admite un solo alto, que se define mediante el tamaño de fuente del control. En un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el diseño dinámico, que supone que los elementos se pueden expandir verticalmente, un control de <xref:System.Windows.Forms.ComboBox> hospedado no se ajustará según lo esperado.  
  
- Windows Forms controles no se pueden girar ni sesgar. Por ejemplo, al girar la interfaz de usuario en 90 grados, los controles de Windows Forms hospedados mantendrán su posición vertical.  
  
- En la mayoría de los casos, los controles de Windows Forms no admiten el escalado proporcional. Aunque las dimensiones generales del control se escalarán, los controles secundarios y los elementos de los componentes del control podrían no cambiar de tamaño según lo previsto. Esta limitación depende de cómo cada control Windows Forms admita el escalado.  
  
- En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición. Un control de Windows Forms hospedado se dibuja en un HWND independiente, por lo que siempre se dibuja encima de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Windows Forms controles admiten el escalado automático en función del tamaño de fuente. En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño de todo el diseño, aunque es posible que algunos elementos cambien de tamaño dinámicamente.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las propiedades de ambiente de los controles [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen Windows Forms equivalentes. Estas propiedades de ambiente se propagan a los controles de Windows Forms hospedados y se exponen como propiedades públicas en el control de <xref:System.Windows.Forms.Integration.WindowsFormsHost>. El control <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte cada propiedad de ambiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en su Windows Forms equivalente.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|admitido|No compatibles|  
|--------------|---------------|-------------------|  
|Transparencia|La representación de controles Windows Forms admite la transparencia. El fondo del control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] primario puede convertirse en el fondo de los controles de Windows Forms hospedados.|Algunos controles Windows Forms no admiten la transparencia. Por ejemplo, los controles <xref:System.Windows.Forms.TextBox> y <xref:System.Windows.Forms.ComboBox> no serán transparentes cuando se hospeden en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Tabulación|El orden de tabulación de los controles de Windows Forms hospedados es el mismo que cuando estos controles se hospedan en una aplicación basada en Windows Forms.<br /><br /> La tabulación de un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un control de Windows Forms con la tecla TAB y las teclas MAYÚS + TAB funciona de la forma habitual.<br /><br /> Windows Forms controles que tienen un valor de propiedad <xref:System.Windows.Forms.Control.TabStop%2A> de `false` no reciben el foco cuando el usuario se desplaza por los controles.<br /><br /> -Cada control <xref:System.Windows.Forms.Integration.WindowsFormsHost> tiene un valor <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>, que determina cuándo el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> recibirá el foco.<br />-Windows Forms controles incluidos en un contenedor de <xref:System.Windows.Forms.Integration.WindowsFormsHost> siguen el orden especificado por la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>. La tabulación desde el último índice de tabulación sitúa el foco en el siguiente control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en el caso de que haya alguno. Si no existe ningún otro control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, la tabulación vuelve al primer control Windows Forms en el orden de tabulación.<br />-   los valores <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> de los controles dentro de la <xref:System.Windows.Forms.Integration.WindowsFormsHost> son relativos a los controles de Windows Forms relacionados contenidos en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />- La tabulación respeta el comportamiento específico del control. Por ejemplo, al presionar la tecla TAB en un control <xref:System.Windows.Forms.TextBox> que tiene un valor de propiedad <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> de `true` se escribe una tabulación en el cuadro de texto en lugar de mover el foco.|No es aplicable.|  
|Navegación con las teclas de dirección|-La navegación con las teclas de dirección en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> es igual que en un control contenedor de Windows Forms ordinario: las teclas de flecha arriba y flecha izquierda seleccionan el control anterior, y las teclas de flecha abajo y flecha derecha seleccionan el control siguiente.<br />-Las teclas flecha arriba y flecha izquierda del primer control contenido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> realizan la misma acción que el método abreviado de teclado MAYÚS + TAB. Si hay un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, el foco se mueve fuera del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Este comportamiento difiere del comportamiento de <xref:System.Windows.Forms.ContainerControl> estándar en que no se produce ningún ajuste en el último control. Si no existe ningún otro control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, el foco vuelve al último control Windows Forms en el orden de tabulación.<br />-Las teclas de flecha abajo y derecha del último control contenido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> realizan la misma acción que la tecla TAB. Si hay un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, el foco se mueve fuera del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Este comportamiento difiere del comportamiento de <xref:System.Windows.Forms.ContainerControl> estándar en que no se produce ningún ajuste en el primer control. Si no existe ningún otro control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, el foco vuelve al primer control Windows Forms en el orden de tabulación.|No es aplicable.|  
|Aceleradores|Los aceleradores funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|Los aceleradores duplicados entre tecnologías no funcionan como los aceleradores duplicados normales. Cuando se duplica un acelerador entre tecnologías, con al menos uno en un control Windows Forms y el otro en un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control Windows Forms siempre recibe el acelerador. El foco no alterna entre los controles cuando se presiona el acelerador duplicado.|  
|Teclas de método abreviado|Las teclas de método abreviado funcionan como de costumbre, excepto donde se indique en la columna "No compatible".|-Windows Forms teclas de método abreviado que se controlan en la fase de preprocesamiento siempre tienen prioridad sobre las teclas de método abreviado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Por ejemplo, si tiene un control <xref:System.Windows.Forms.ToolStrip> con las teclas de método abreviado CTRL + S definidas, y hay un comando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlazado a CTRL + S, siempre se invoca primero el controlador de control <xref:System.Windows.Forms.ToolStrip>, independientemente del foco.<br />-Windows Forms teclas de método abreviado controladas por el evento <xref:System.Windows.Forms.Control.KeyDown> se procesan en último lugar en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Puede evitar este comportamiento invalidando el método de <xref:System.Windows.Forms.Control.IsInputKey%2A> del control Windows Forms o controlando el evento <xref:System.Windows.Forms.Control.PreviewKeyDown>. Devuelva `true` del método <xref:System.Windows.Forms.Control.IsInputKey%2A> o establezca el valor de la propiedad <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> en `true` en el controlador de eventos <xref:System.Windows.Forms.Control.PreviewKeyDown>.|  
|AcceptsReturn, AcceptsTab y otros comportamientos específicos del control|Las propiedades que cambian el comportamiento predeterminado del teclado funcionan como de costumbre, suponiendo que el control Windows Forms invalida el método <xref:System.Windows.Forms.Control.IsInputKey%2A> para devolver `true`.|Windows Forms controles que cambian el comportamiento predeterminado del teclado mediante el control del evento de <xref:System.Windows.Forms.Control.KeyDown> se procesan en último lugar en el control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del host. Dado que estos controles se procesan en último lugar, pueden dar lugar a un comportamiento inesperado.|  
|Eventos Enter y Leave|Cuando el foco no va al control contenedor <xref:System.Windows.Forms.Integration.ElementHost>, los eventos Enter y Leave se generan como de costumbre cuando el foco cambia en un único control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|Los eventos Enter and Leave no se generan cuando se producen los siguientes cambios en el foco:<br /><br /> -Desde dentro o fuera de un control de <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-Desde fuera hacia dentro de un control de <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-Fuera de un control de <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-Desde un control de Windows Forms hospedado en un control de <xref:System.Windows.Forms.Integration.WindowsFormsHost> a un control de <xref:System.Windows.Forms.Integration.ElementHost> hospedado en la misma <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Multithreading|Se admiten todas las variedades de multithreading.|Las tecnologías Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] suponen un modelo de simultaneidad de un solo subproceso. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|de seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de Asistencia funcionan correctamente cuando se utilizan para aplicaciones híbridas que contienen controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar entre los controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre los controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hospedar controles de WPF en Windows Forms  
 Se admiten los siguientes escenarios de interoperación cuando un control Windows Forms hospeda un control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Hospedar uno o varios controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  
  
- Asociar una hoja de propiedades con uno o varios controles hospedados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar una o varias páginas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un formulario.  
  
- Iniciar una ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar un formulario principal/detalle con un Windows Forms maestro y detalles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar un formulario principal/detalle con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] maestro y detalles de Windows Forms.  
  
- Hospedar controles personalizados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hospedar controles híbridos.  
  
### <a name="ambient-properties"></a>Propiedades ambiente  
 Algunas de las propiedades de ambiente de los controles Windows Forms tienen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalentes. Estas propiedades de ambiente se propagan a los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados y se exponen como propiedades públicas en el control de <xref:System.Windows.Forms.Integration.ElementHost>. El control <xref:System.Windows.Forms.Integration.ElementHost> convierte cada propiedad de ambiente Windows Forms en su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalente.  
  
 Para más información, vea [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|admitido|No compatibles|  
|--------------|---------------|-------------------|  
|Transparencia|La representación de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite la transparencia. El fondo del control de Windows Forms primario puede convertirse en el fondo de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados.|No es aplicable.|  
|Multithreading|Se admiten todas las variedades de multithreading.|Las tecnologías Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] suponen un modelo de simultaneidad de un solo subproceso. Durante la depuración, las llamadas a objetos de framework desde otros subprocesos provocarán una excepción para aplicar este requisito.|  
|de seguridad|Todos los escenarios de interoperación requieren plena confianza.|No se permite ningún escenario de interoperación con confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad. Los productos de tecnología de Asistencia funcionan correctamente cuando se utilizan para aplicaciones híbridas que contienen controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre. Esto incluye cortar y pegar entre los controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre. Esto incluye las operaciones entre los controles Windows Forms y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Tutorial: Hospedar un control de Windows Forms en WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Asignación de propiedades en formularios Windows Forms y WPF](windows-forms-and-wpf-property-mapping.md)
