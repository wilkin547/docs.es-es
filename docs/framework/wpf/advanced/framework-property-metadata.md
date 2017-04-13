---
title: "Metadatos de las propiedades de marco de trabajo | Microsoft Docs"
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
  - "metadatos de las propiedades del marco de trabajo"
  - "metadatos, propiedades del marco de trabajo"
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Metadatos de las propiedades de marco de trabajo
Las opciones de metadatos de las propiedades de marco de trabajo se comunican para las propiedades de elementos de objeto que se consideran presentes en el [nivel de marco de trabajo de WPF](GTMT) en la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  En general, la designación de [nivel de marco de trabajo de WPF](GTMT) conlleva que determinadas características, tales como la representación, los enlaces de datos y las matizaciones del sistema de propiedades, las administren las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] y los archivos ejecutables de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Estos sistemas consultan los metadatos de las propiedades de marco de trabajo para determinar las particularidades específicas de las características de las propiedades de determinados elementos.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se da por sentado que entiende las [propiedades de dependencia](GTMT) desde la perspectiva de un consumidor de las propiedades de dependencia existentes en las clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], y que ha leído [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  También, debería haber leído [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## Información comunicada por los metadatos de las propiedades de marco de trabajo  
 Los metadatos de las propiedades de marco de trabajo se pueden dividir en las categorías siguientes:  
  
-   Comunicación de propiedades de diseño que afectan a un elemento \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>\).  Puede establecer estos marcadores de los metadatos si la propiedad afecta a esos aspectos respectivos, y si también implementa los métodos <xref:System.Windows.FrameworkElement.MeasureOverride%2A> \/ <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> de la clase para proporcionar al sistema del diseño comportamiento e información de representación concretos.  Normalmente, este tipo de implementación comprobaría las invalidaciones de propiedad en las propiedades de dependencia para aquellos casos en que se cumpliese cualquiera de estas propiedades de diseño en los metadatos de propiedad, y sólo esas invalidaciones tendrían que solicitar un nuevo paso de diseño.  
  
-   Comunicación de propiedades de diseño que afectan al elemento primario de un elemento \(<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>\).  Algunos ejemplos en que se establecen estos marcadores de manera predeterminada son <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=fullName> y <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=fullName>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>.  De forma predeterminada, las propiedades de dependencia no heredan los valores.  <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> permite a la ruta de herencia recorrer también el interior de un árbol visual, algo que es necesario para algunos escenarios de composición de controles.  
  
    > [!NOTE]
    >  El término "heredar" en el contexto de los valores de propiedad tiene un significado concreto para las propiedades de dependencia: significa que los elementos secundarios pueden heredar el valor de la propiedad de dependencia real de los elementos primarios gracias a una función de [nivel de marco de trabajo de WPF](GTMT) del sistemas de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  No tiene nada que ver directamente con la herencia de miembros y tipos de código administrado a través de tipos derivados.  Para obtener información detallada, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
-   Comunicación de características de enlace de datos \(<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>\).  De manera predeterminada, las propiedades de dependencia del marco de trabajo admiten el enlace de datos, con un comportamiento de enlace unidireccional.  Puede deshabilitar el enlace de datos si no existe ningún escenario para ello en absoluto \(dado que se pretende que sean flexibles y extensibles, no hay muchos ejemplos de este tipo de propiedades en las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] predeterminadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\).  Puede establecer el enlace de modo que su valor predeterminado sea bidireccional para las propiedades que conectan entre sí los comportamientos de un control entre los elementos que lo componen \(<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> es un ejemplo de ello\) o en aquellos casos en que el enlace bidireccional sea el escenario común esperado por los usuarios \(<xref:System.Windows.Controls.TextBox.Text%2A> es un ejemplo de ello\).  Cambiar los metadatos relacionados con el enlace de datos afecta únicamente al valor predeterminado; este valor siempre se puede modificar para cada enlace.  Para obtener detalles sobre los modos de enlace y el enlace en general, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Comunicación de si las aplicaciones o los servicios compatibles con el diario deben incluir en él las propiedades \(<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>\).  Para los elementos generales, la inclusión en el diario no está habilitada de manera predeterminada, sino que se habilita de manera selectiva para algunos controles de datos proporcionados por el usuario.  Esta propiedad sirve para que la lean los servicios de diario, incluida la implementación del diario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], y suele establecerse para controles de usuario tales como selecciones del usuario en listas que deben conservarse en los pasos de navegación subsiguientes.  Para obtener más información sobre el diario, vea [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## Leer FrameworkPropertyMetadata  
 Cada una de las propiedades vinculadas anteriormente son propiedades específicas que <xref:System.Windows.FrameworkPropertyMetadata> agrega a su clase base <xref:System.Windows.UIPropertyMetadata> inmediata.  Cada una de estas propiedades es `false` de manera predeterminada.  Una solicitud de metadatos de una propiedad cuando es importante conocer el valor de estas propiedades debe intentar convertir los metadatos devueltos en <xref:System.Windows.FrameworkPropertyMetadata> y, a continuación, comprobar los valores de las propiedades individuales según sea necesario.  
  
<a name="Specifying_Metadata"></a>   
## Especificar los metadatos  
 Cuando se crea una nueva instancia de metadatos a fin de aplicarlos a un nuevo registro de propiedad de dependencia, puede elegir la clase de metadatos que desea utilizar: la clase base <xref:System.Windows.PropertyMetadata> o alguna clase derivada, como <xref:System.Windows.FrameworkPropertyMetadata>.  En general, debe utilizar <xref:System.Windows.FrameworkPropertyMetadata>, en especial si la propiedad tiene alguna interacción con el sistema de propiedades y las funciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], como las de diseño y el enlace de datos.  Otra opción para escenarios más sofisticados consiste en derivar de <xref:System.Windows.FrameworkPropertyMetadata> a fin de crear su propia clase de comunicación de metadatos cuyos miembros contengan información adicional.  O también puede utilizar <xref:System.Windows.PropertyMetadata> o <xref:System.Windows.UIPropertyMetadata> para comunicar el grado de compatibilidad con las características de la implementación.  
  
 Para las propiedades existentes \(llamada a <xref:System.Windows.DependencyProperty.AddOwner%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>\), debe invalidar siempre con el tipo de metadatos utilizado por el registro original.  
  
 Si crea una instancia de <xref:System.Windows.FrameworkPropertyMetadata>, hay dos maneras de rellenar esos metadatos con valores correspondientes a las propiedades concretas que comunican las características de las propiedades de marco de trabajo:  
  
1.  Utilice la firma de constructor de <xref:System.Windows.FrameworkPropertyMetadata>, que permite un parámetro `flags`.  Este parámetro debe rellenarse con todos los valores combinados deseados de los marcadores de enumeración de <xref:System.Windows.FrameworkPropertyMetadataOptions>.  
  
2.  Utilice una de las firmas sin un parámetro `flags` y, a continuación, establezca la propiedad Boolean de comunicación de <xref:System.Windows.FrameworkPropertyMetadata> en `true` para cada cambio de característica deseado.  Si lo hace, debe establecer estas propiedades antes de construir cualquier elemento con esta propiedad de dependencia; las propiedades Boolean son de lectura y escritura a fin de permitir este comportamiento consistente en evitar el parámetro `flags` y, aún así, rellenar los metadatos, pero los metadatos deben quedar sellados de manera efectiva antes de utilizar la propiedad.  Así pues, si intenta establecer las propiedades después de solicitar los metadatos, la operación no será válida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## Comportamiento de combinación de metadatos de propiedades de marco de trabajo  
 Cuando se invalidan los metadatos de propiedades de marco de trabajo, las distintas características de los metadatos se combinan o reemplazan.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se combina.  Si agrega una nueva <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, esa devolución de llamada se almacena en los metadatos.  Si no especifica una <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se promueve como una referencia del antecesor más próximo que lo especifique en los metadatos.  
  
-   El comportamiento del sistema de propiedades real para <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> es que se retienen las implementaciones correspondientes a todos los propietarios de metadatos de la jerarquía y se agregan a una tabla, de tal forma que el orden de ejecución en el sistema de propiedades consiste en invocar primero las devoluciones de llamada de la clase derivada más profundamente.  Las devoluciones de llamada heredadas sólo se ejecutan una vez, y cuentan como propiedad de la clase que las colocó en los metadatos.  
  
-   Se reemplaza <xref:System.Windows.PropertyMetadata.DefaultValue%2A>.  Si no especifica una <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.DefaultValue%2A> procede del antecesor más próximo que lo especifique en los metadatos.  
  
-   Se reemplazan las implementaciones de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>.  Si agrega una nueva <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, esa devolución de llamada se almacena en los metadatos.  Si no especifica una <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se promueve como una referencia del antecesor más próximo que lo especifique en los metadatos.  
  
-   El comportamiento del sistema de propiedades consiste en invocar únicamente la <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> de los metadatos inmediatos.  Se retiene ninguna referencia a otras implementaciones de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la jerarquía.  
  
-   Las marcas de la enumeración <xref:System.Windows.FrameworkPropertyMetadataOptions> se combinan como una operación OR bit a bit.  Si especifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, las opciones originales no se sobrescriben.  Para cambiar una opción, establezca la propiedad correspondiente en <xref:System.Windows.FrameworkPropertyMetadata>.  Por ejemplo, si el objeto <xref:System.Windows.FrameworkPropertyMetadata> original establece la marca <xref:System.Windows.FrameworkPropertyMetadataOptions?displayProperty=fullName>, puede cambiarlo estableciendo <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=fullName> en `false`.  
  
 Este comportamiento se implementa mediante <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A> y se puede reemplazar en las clases de metadatos derivadas.  
  
## Vea también  
 <xref:System.Windows.DependencyProperty.GetMetadata%2A>   
 [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)