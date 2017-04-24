---
title: "Interoperabilidad entre Windows Forms y WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control híbrido [interoperabilidad con WPF]"
  - "interoperabilidad [WPF], Windows Forms"
  - "interoperación de anidación [WPF]"
  - "formularios Windows Forms [WPF], interoperabilidad con"
  - "Windows Forms, interoperabilidad con WPF"
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Interoperabilidad entre Windows Forms y WPF
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] presentan dos arquitecturas diferentes para crear interfaces de aplicaciones.  El espacio de nombres <xref:System.Windows.Forms.Integration?displayProperty=fullName> proporciona clases que habilitan los escenarios de interoperación más comunes.  Las dos clases clave que implementan las funciones de interoperación son <xref:System.Windows.Forms.Integration.WindowsFormsHost> y <xref:System.Windows.Forms.Integration.ElementHost>.  En este tema se describe qué escenarios de interoperación se admiten y cuáles no.  
  
> [!NOTE]
>  Se presta especial atención al escenario de *control híbrido*.  Un control híbrido tiene un control de una tecnología anidado en un control de otra tecnología.  También se denomina una *interoperación anidada*.  Un *control híbrido de varios niveles* tiene más de un nivel de anidamiento de controles híbridos.  Un ejemplo de una interoperación anidada de varios niveles es un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que contiene un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que contiene otro control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  No se admiten los controles híbridos de varios niveles.  
  
   
  
<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## Hospedar controles de Windows Forms en WPF  
 Se admiten los escenarios de interoperación siguientes cuando un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospeda un control de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]:  
  
-   El control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] puede hospedar uno o más controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mediante XAML.  
  
-   Puede hospedar uno o más controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mediante código.  
  
-   Puede hospedar controles contenedores de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que contienen otros controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Puede hospedar un formulario principal\-detalle con un elemento principal de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y detalles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Puede hospedar un formulario principal\-detalle con un elemento principal de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y detalles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Puede hospedar uno o más controles [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)].  
  
-   Puede hospedar uno o más controles compuestos.  
  
-   Puede hospedar controles híbridos mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
-   Puede hospedar controles híbridos mediante código.  
  
### Compatibilidad de diseño  
 En la lista siguiente se describen las limitaciones conocidas cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta integrar su control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   En algunos casos, no se puede cambiar el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o únicamente se pueden ajustar a dimensiones concretas.  Por ejemplo, un control <xref:System.Windows.Forms.ComboBox> de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] únicamente admite un alto, que se define basándose en el tamaño de fuente de control.  En un diseño dinámico de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], en que se da por hecho que los elementos pueden ajustarse verticalmente, un control <xref:System.Windows.Forms.ComboBox> hospedado no se ajustará según lo esperado.  
  
-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se pueden girar ni sesgar.  Por ejemplo, al girar la interfaz de usuario 90 grados, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados mantendrán su posición vertical.  
  
-   En la mayoría de los casos, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el ajuste de escala proporcional.  Aunque se ajustará la escala de las dimensiones totales del control, es posible que el tamaño de los controles secundarios y de los elementos componentes del control no cambien según lo esperado.  Esta limitación depende de en qué medida admita cada control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] el ajuste de escala.  
  
-   En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición.  Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado se dibuja en un indicador de ventana \(HWND\) independiente, por lo que siempre se dibuja encima de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admiten el ajuste automático de escala basado en el tamaño de fuente.  En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño del diseño completo, aunque es posible que algunos elementos individuales ajusten su tamaño dinámicamente.  
  
### Propiedades de ambiente  
 Algunas de las propiedades de ambiente de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen equivalentes en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Estas propiedades de ambiente se propagan a los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados y expuestos como propiedades públicas en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  El control <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte cada propiedad de ambiente de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en su equivalente en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Para obtener más información, consulte [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------------|----------------|-------------------|  
|Transparencia|La representación de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admite la transparencia.  El fondo del control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] primario se puede convertir en el fondo de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados.|Algunos controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten la transparencia.  Por ejemplo, los controles <xref:System.Windows.Forms.TextBox> y <xref:System.Windows.Forms.ComboBox> no serán transparentes cuando se hospeden en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Desplazamiento mediante la tecla TAB|El orden de desplazamiento mediante la tecla TAB para los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados es el mismo que cuando dichos controles se encuentran hospedados en una aplicación basada en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> El desplazamiento desde un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hasta un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] utilizando la tecla TAB y las teclas MAYÚS\+TAB funciona del modo habitual.<br /><br /> Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que tienen una propiedad <xref:System.Windows.Forms.Control.TabStop%2A> establecida en el valor `false` no reciben el foco cuando el usuario se desplaza de un control a otro mediante la tecla TAB.<br /><br /> -   Cada control <xref:System.Windows.Forms.Integration.WindowsFormsHost> tiene un valor de <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>, que determina cuándo ese control <xref:System.Windows.Forms.Integration.WindowsFormsHost> recibirá el foco.<br />-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contenidos en un contenedor de <xref:System.Windows.Forms.Integration.WindowsFormsHost> siguen el orden especificado por la propiedad <xref:System.Windows.Forms.Control.TabIndex%2A>.  Al presionar la tecla TAB desde el último índice de tabulación, el foco pasa al siguiente control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], si lo hay.  Si no hay ningún otro control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, al presionar la tecla TAB el foco regresa al primer control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] según el orden de tabulación.<br />-   Los valores de <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> para los controles contenidos en <xref:System.Windows.Forms.Integration.WindowsFormsHost> son relativos a los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] relacionados contenidos en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   El desplazamiento mediante la tecla TAB respeta el comportamiento específico de los controles.  Por ejemplo, al presionar la tecla TAB en un control <xref:System.Windows.Forms.TextBox> cuya propiedad <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> está establecida en el valor `true`, se escribe una tabulación en el cuadro de texto, en lugar de mover el foco.|No es aplicable|  
|Navegación con las teclas de dirección|-   La navegación con las teclas de dirección en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> es igual que en un control contenedor de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ordinario: las teclas de dirección ARRIBA e IZQUIERDA seleccionan el control anterior, mientras que las teclas de dirección ABAJO y DERECHA seleccionan el control siguiente.<br />-   Las teclas de dirección ARRIBA e IZQUIERDA del primer control contenido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> realizan la misma acción que el método abreviado de teclado MAYÚS\+TAB.  Si hay un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puede recibir el foco, éste sale del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Este comportamiento difiere del comportamiento de <xref:System.Windows.Forms.ContainerControl> estándar en que no se produce ningún ajuste al último control.  Si no hay ningún otro control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, este vuelve al último control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] según el orden de tabulación.<br />-   Las teclas de dirección ABAJO y DERECHA del último control contenido en el control <xref:System.Windows.Forms.Integration.WindowsFormsHost> realizan la misma acción que la tecla TAB.  Si hay un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puede recibir el foco, éste sale del control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  Este comportamiento difiere del comportamiento de <xref:System.Windows.Forms.ContainerControl> estándar en que no se produce ningún ajuste al primer control.  Si no hay ningún otro control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que pueda recibir el foco, éste vuelve al primer control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] según el orden de tabulación.|No es aplicable|  
|Aceleradores|Los aceleradores funcionan como de costumbre, excepto cuando se indique otra cosa en la columna "No compatible".|Los aceleradores duplicados entre tecnologías no funcionan como los aceleradores duplicados ordinarios.  Cuando un acelerador se duplica entre dos tecnologías, y al menos uno de ellos se encuentra en un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y el otro en un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] recibe siempre el acelerador.  El foco no alterna entre los dos controles cuando se presiona el acelerador duplicado.|  
|Teclas de método abreviado|Las teclas de método abreviado funcionan como de costumbre, excepto cuando se indique otra cosa en la columna "No compatible".|-   Las teclas de método abreviado de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que se administran en la fase de preprocesamiento siempre tienen preferencia sobre las teclas de método abreviado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Por ejemplo, si tiene un control <xref:System.Windows.Forms.ToolStrip> para el que se han definido las teclas de método abreviado CTRL\+S, y hay un comando de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enlazado a CTRL\+S, siempre se invoca primero el controlador del control <xref:System.Windows.Forms.ToolStrip>, sin tener en cuenta el foco.<br />-   Las teclas de método abreviado de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que se controlan mediante el evento <xref:System.Windows.Forms.Control.KeyDown> se procesan en último lugar en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Puede evitar este comportamiento invalidando el método <xref:System.Windows.Forms.Control.IsInputKey%2A> del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o controlando el evento <xref:System.Windows.Forms.Control.PreviewKeyDown>.  Devuelva `true` del método <xref:System.Windows.Forms.Control.IsInputKey%2A> o establezca el valor de la propiedad <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=fullName> en `true` en el controlador de eventos <xref:System.Windows.Forms.Control.PreviewKeyDown>.|  
|AcceptsReturn, AcceptsTab y otros comportamientos específicos del control|Las propiedades que cambian el comportamiento predeterminado del teclado funcionan como de costumbre, suponiendo que el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] invalide el método <xref:System.Windows.Forms.Control.IsInputKey%2A> para devolver `true`.|Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que cambian el comportamiento predeterminado del teclado controlando el evento <xref:System.Windows.Forms.Control.KeyDown> se procesan en último lugar en el control host de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Dado que estos controles se procesan en último lugar, pueden dar lugar a comportamientos inesperados.|  
|Eventos Enter y Leave|Cuando el foco no va al control contenedor <xref:System.Windows.Forms.Integration.ElementHost>, se provocan los eventos Enter y Leave como de costumbre cuando el foco cambia en un control <xref:System.Windows.Forms.Integration.WindowsFormsHost> único.|Los eventos Enter y Leave no se provocan cuando se producen los cambios de foco siguientes:<br /><br /> -   Del interior al exterior de un control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   Del exterior al interior de un control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   Fuera de un control <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-   De un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en un control <xref:System.Windows.Forms.Integration.WindowsFormsHost> a un control <xref:System.Windows.Forms.Integration.ElementHost> hospedado dentro del mismo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Multithreading|Se admiten todas las variedades de multithreading.|Tanto la tecnología [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] suponen la utilización de un modelo de simultaneidad de un solo subproceso.  Durante la depuración, las llamadas a los objetos de marco de otros subprocesos iniciarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|Ningún escenario de interoperación se permite en confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad.  Los productos de tecnología de ayuda funcionan correctamente cuando se utilizan para aplicaciones híbridas que contienen controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre.  Esto incluye cortar y pegar entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre.  Esto incluye las operaciones entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## Hospedar controles de WPF en Windows Forms  
 Se admiten los escenarios de interoperación siguientes cuando un control de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] hospeda un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Hospedar uno o varios controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mediante código.  
  
-   Asociar una hoja de propiedades a uno o más controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados.  
  
-   Hospedar una o más páginas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un formulario.  
  
-   Iniciar una ventana de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Hospedar un formulario principal\-detalle con un elemento principal de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y detalles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Hospedar un formulario principal\-detalle con un elemento principal de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y detalles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Hospedar controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] personalizados.  
  
-   Hospedar controles híbridos.  
  
### Propiedades de ambiente  
 Algunas de las propiedades de ambiente de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tienen equivalentes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Estas propiedades de ambiente se propagan a los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados y expuestos como propiedades públicas en el control <xref:System.Windows.Forms.Integration.ElementHost>.  El control <xref:System.Windows.Forms.Integration.ElementHost> convierte cada propiedad de ambiente de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en su equivalente en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para obtener más información, consulte [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Comportamiento  
 En la tabla siguiente se describe el comportamiento de interoperación.  
  
|Comportamiento|Compatible|No compatible|  
|--------------------|----------------|-------------------|  
|Transparencia|La representación de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admite la transparencia.  El fondo del control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] primario se puede convertir en el fondo de los controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedados.|No es aplicable|  
|Multithreading|Se admiten todas las variedades de multithreading.|Tanto la tecnología [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] suponen la utilización de un modelo de simultaneidad de un solo subproceso.  Durante la depuración, las llamadas a los objetos de marco de otros subprocesos iniciarán una excepción para aplicar este requisito.|  
|Seguridad|Todos los escenarios de interoperación requieren plena confianza.|Ningún escenario de interoperación se permite en confianza parcial.|  
|Accesibilidad|Se admiten todos los escenarios de accesibilidad.  Los productos de tecnología de ayuda funcionan correctamente cuando se utilizan para aplicaciones híbridas que contienen controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
|Portapapeles|Todas las operaciones del Portapapeles funcionan como de costumbre.  Esto incluye cortar y pegar entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
|Característica de arrastrar y colocar|Todas las operaciones de arrastrar y colocar funcionan como de costumbre.  Esto incluye las operaciones entre controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|No es aplicable|  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)