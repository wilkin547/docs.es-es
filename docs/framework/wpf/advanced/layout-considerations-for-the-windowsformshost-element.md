---
title: "Consideraciones sobre el dise&#241;o del elemento WindowsFormsHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "píxeles independientes de dispositivo"
  - "diseño dinámico [interoperabilidad con WPF]"
  - "interoperabilidad [WPF], Windows Forms"
  - "formularios Windows Forms [WPF], interoperabilidad con"
  - "Windows Forms, interoperabilidad con WPF"
  - "consideraciones sobre el diseño de elementos WindowsFormsHost"
ms.assetid: 3c574597-bbde-440f-95cc-01371f1a5d9d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Consideraciones sobre el dise&#241;o del elemento WindowsFormsHost
En este tema se describe cómo interactúa el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> con el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admiten lógicas diferentes, pero similares, para dimensionar y colocar los elementos en un formulario o una página.  Cuando se crea una interfaz de usuario híbrida que hospeda controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> integra los dos esquemas del diseño.  
  
## Diferencias de diseño entre WPF y Windows Forms  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utiliza un diseño independiente de la resolución.  Todas las dimensiones de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se especifican mediante *píxeles independientes del dispositivo*.  Un píxel independiente del dispositivo tiene un tamaño de 1\/96 de pulgada y es independiente de la resolución, por lo que obtiene resultados similares independientemente de si se representa en un monitor de 72 ppp o en una impresora de 19.200 ppp.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también se basa en el *diseño dinámico*.  Esto significa que un elemento de la interfaz de usuario se organiza en un formulario o una página según su contenido, su contenedor de diseño primario y el tamaño de pantalla disponible.  El diseño dinámico facilita la localización ajustando automáticamente el tamaño y la posición de los elementos de la interfaz de usuario cuando cambia la longitud de las cadenas que contienen.  
  
 En [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], el diseño es dependiente del dispositivo y tiene mayor probabilidad de ser estático.  Normalmente, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] se colocan de manera absoluta en el formulario utilizando dimensiones especificadas en píxeles de hardware.  Sin embargo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admite algunas características de diseño dinámico, que se resumen en la tabla siguiente.  
  
|Característica de diseño|Descripción|  
|------------------------------|-----------------|  
|Ajuste automático de tamaño|Algunos controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ajustan su tamaño para mostrar correctamente el contenido.  Para obtener más información, consulte [Información general sobre la propiedad AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).|  
|Delimitación y acoplamiento|Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] permiten la colocación y el dimensionamiento basados en el contenedor primario.  Para obtener más información, vea <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName> y <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>.|  
|Ajuste automático de escala|Los controles contenedores ajustan su tamaño y el de sus elementos secundarios de acuerdo con la resolución del dispositivo de salida o con el tamaño, en píxeles, de la fuente del contenedor predeterminada.  Para obtener más información, consulte [Ajuste automático de escala en formularios Windows Forms](../../../../docs/framework/winforms/automatic-scaling-in-windows-forms.md).|  
|Contenedores de diseño|Los controles <xref:System.Windows.Forms.FlowLayoutPanel> y <xref:System.Windows.Forms.TableLayoutPanel> organizan sus controles secundarios y ajustan su tamaño de acuerdo con su contenido.|  
  
## Limitaciones de diseño  
 En general, no es posible ajustar la escala de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ni transformarlos en la misma medida que los de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En la lista siguiente se describen las limitaciones conocidas cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta integrar su control [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado en el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   En algunos casos, no se puede cambiar el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] o únicamente se pueden ajustar a dimensiones concretas.  Por ejemplo, un control <xref:System.Windows.Forms.ComboBox> de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] únicamente admite un alto, que se define basándose en el tamaño de fuente de control.  En un diseño dinámico de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] donde los elementos pueden ajustarse verticalmente, un control <xref:System.Windows.Forms.ComboBox> hospedado no se ajustará según lo esperado.  
  
-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no se pueden girar ni sesgar.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> provoca el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> si se aplica una transformación de sesgo o giro.  Si no controla el evento <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError>, se inicia una excepción <xref:System.InvalidOperationException>.  
  
-   En la mayoría de los casos, los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admiten el ajuste de escala proporcional.  Aunque se ajustará la escala de las dimensiones totales del control, es posible que el tamaño de los controles secundarios y de los elementos componentes del control no cambien según lo esperado.  Esta limitación depende de en qué medida admita cada control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] el ajuste de escala.  Además, no puede reducir el tamaño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a 0 píxeles.  
  
-   Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] admiten el ajuste de escala automático, según el cual el formulario cambiará automáticamente su propio tamaño y el de sus controles de acuerdo con el tamaño de fuente.  En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], al cambiar el tamaño de fuente no se cambia el tamaño del diseño completo, aunque es posible que algunos elementos individuales ajusten su tamaño dinámicamente.  
  
### Orden z  
 En una interfaz de usuario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], puede cambiar el orden z de los elementos para controlar el comportamiento de superposición.  Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado se dibuja en un indicador de ventana \(HWND\) independiente, por lo que siempre se dibuja encima de los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Un control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado también se dibuja encima de todos los elementos <xref:System.Windows.Documents.Adorner>.  
  
## Comportamiento de diseño  
 En las secciones siguientes se describen aspectos concretos del comportamiento de diseño al hospedar controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Ajuste de escala, conversión de unidades e independencia del dispositivo  
 Siempre que el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> realiza operaciones que implican dimensiones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], se utilizan dos sistemas de coordenadas: los píxeles independientes del dispositivo para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y los píxeles de hardware para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Por consiguiente, debe aplicar las conversiones de unidades y escala apropiadas para lograr un diseño coherente.  
  
 La conversión entre los sistemas de coordenadas depende de la resolución del dispositivo actual y de cualquier transformación de diseño o representación que se aplique al elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> o a sus antecesores.  
  
 Si el dispositivo de salida es de 96 ppp y no se aplica ningún ajuste de escala al elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost>, un píxel independiente del dispositivo es igual a un píxel de hardware.  
  
 En todos los demás casos es preciso ajustar la escala del sistema de coordenadas.  El tamaño del control hospedado no cambia.  En su lugar, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> intenta ajustar la escala del control hospedado y de todos sus controles secundarios.  Dado que [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] no admite plenamente el ajuste de escala, la escala del elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se ajusta en la medida en que lo admitan los distintos controles concretos.  
  
 Invalide el método <xref:System.Windows.Forms.Integration.WindowsFormsHost.ScaleChild%2A> para proporcionar un comportamiento de ajuste de escala personalizado para el control hospedado de [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].  
  
 Además del ajuste de la escala, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> controla los casos de redondeo y desbordamiento tal y como se describe en la tabla siguiente.  
  
|Problema de conversión|Descripción|  
|----------------------------|-----------------|  
|Redondeo|Las dimensiones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en píxeles independientes del dispositivo se especifican como `double`, y las dimensiones de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] en píxeles de hardware se especifican como `int`.  En los casos en que se convierten dimensiones basadas en el tipo `double` en dimensiones basadas en el tipo `int`, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utiliza el redondeo estándar, para que los valores fraccionarios menores que 0,5 se redondeen a 0.|  
|Desbordamiento|Cuando el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> convierte valores `double` en valores `int`, es posible que se produzca desbordamiento.  Los valores mayores que <xref:System.Int32.MaxValue> se establecen en <xref:System.Int32.MaxValue>.|  
  
### Propiedades relacionadas con el diseño  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> asigna correctamente las propiedades que controlan el comportamiento de diseño de los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] y los elementos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información, consulte [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
### Cambios de diseño en el control hospedado  
 Los cambios de diseño en los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedados se propagan a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para desencadenar actualizaciones del diseño.  El método <xref:System.Windows.UIElement.InvalidateMeasure%2A> de <xref:System.Windows.Forms.Integration.WindowsFormsHost> garantiza que los cambios de diseño del control hospedado provoquen la ejecución del motor de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Controles de formularios Windows Forms con ajuste de tamaño continuo  
 Los controles de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] que admiten el ajuste de escala continuo interactúan plenamente con el sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utiliza como de costumbre los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> para ajustar el tamaño y organizar el control de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hospedado.  
  
### Algoritmo de ajuste de tamaño  
 El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> utiliza el procedimiento siguiente para ajustar el tamaño del control hospedado:  
  
1.  El elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> invalida los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> y <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.  
  
2.  Para determinar el tamaño del control hospedado, el método <xref:System.Windows.FrameworkElement.MeasureOverride%2A> llama al método <xref:System.Windows.Forms.Control.GetPreferredSize%2A> del control hospedado con una restricción traducida a partir de la restricción pasada al método <xref:System.Windows.FrameworkElement.MeasureOverride%2A>.  
  
3.  El método <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> intenta establecer el control hospedado en la restricción de tamaño determinada.  
  
4.  Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> del control hospedado coincide con la restricción especificada, el tamaño del control hospedado se establece en la restricción.  
  
 Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> no coincide con la restricción especificada, el control hospedado no admite el ajuste de tamaño continuo.  Por ejemplo, el control <xref:System.Windows.Forms.MonthCalendar> sólo permite tamaños discretos.  Los tamaños permitidos para este control consisten en números enteros \(que representan el número de meses\) para el alto y el ancho.  En casos como éste, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> se comporta como sigue:  
  
-   Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> devuelve un tamaño mayor que la restricción especificada, el elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> recorta el control hospedado.  El alto y el ancho se controlan por separado, de manera que el control hospedado se puede recortar en cualquier dirección.  
  
-   Si la propiedad <xref:System.Windows.Forms.Control.Size%2A> devuelve un tamaño menor que la restricción especificada, <xref:System.Windows.Forms.Integration.WindowsFormsHost> acepta este valor de tamaño y lo devuelve al sistema de diseño de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Tutorial: Organizar controles de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-arranging-windows-forms-controls-in-wpf.md)   
 [Agregar Controles de Windows Forms en ejemplo de WPF](http://go.microsoft.com/fwlink/?LinkID=159971)   
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)