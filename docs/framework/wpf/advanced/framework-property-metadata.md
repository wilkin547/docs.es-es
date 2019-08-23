---
title: Metadatos de las propiedades de marco de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: c08cf28880d86331e3b561f1749333d401ba903e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964215"
---
# <a name="framework-property-metadata"></a>Metadatos de las propiedades de marco de trabajo
Las opciones de metadatos de propiedad de marco de trabajo se notifican para las propiedades de los elementos de objeto que se consideran presentes en el nivel de marco de trabajo de WPF en la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En general, la designación de nivel de marco de WPF implica que las características como la representación, el enlace de datos y las mejoras del sistema de propiedades se [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlan mediante las API de presentación y los ejecutables. Estos sistemas consultan los metadatos de las propiedades de marco de trabajo para determinar las particularidades específicas de las características de las propiedades de un elemento en particular.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). También debería haber leído [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Información que comunican los metadatos de las propiedades de marco de trabajo  
 Los metadatos de las propiedades de marco de trabajo se pueden dividir en las siguientes categorías:  
  
- Propiedades de diseño de informes que afectan a<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>un <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>elemento <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>(,,). Puede establecer estas marcas en los metadatos si la propiedad afecta a esos aspectos respectivos, y también implementa los <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos de la clase para proporcionar un comportamiento de representación específico e información al diseño. integrado. Normalmente, una implementación tal comprobaría las invalidaciones de propiedad en las propiedades de dependencia donde cualquiera de estas propiedades de diseño fuese verdadera en los metadatos de las propiedades, y solo esas invalidaciones tendrían que solicitar un nuevo paso de diseño.  
  
- Propiedades de diseño de informes que afectan al elemento primario de un<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>elemento <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>(,). Algunos ejemplos en los que estas marcas se establecen de <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> forma <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>predeterminada son y.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> De manera predeterminada, las propiedades de dependencia no heredan los valores. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>permite que la ruta de herencia también viaje a un árbol visual, que es necesario para algunos escenarios de composición de controles.  
  
    > [!NOTE]
    > El término "hereda" en el contexto de los valores de propiedades significa algo específico para las propiedades de dependencia; significa que los elementos secundarios pueden heredar el valor real de la propiedad de dependencia de los elementos primarios debido a una capacidad de nivel de marco de trabajo de WPF del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. No tiene nada que ver directamente con la herencia de tipos y miembros de código administrado a través de tipos derivados. Para obtener información detallada, consulte [Herencia de valores de propiedad](property-value-inheritance.md).  
  
- Características de enlace de datos<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>de <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>informes (,). De manera predeterminada, las propiedades de dependencia en el marco de trabajo admiten el enlace de datos, con un comportamiento de enlace unidireccional. Puede deshabilitar el enlace de datos si no hay ningún escenario para ello (porque están diseñados para ser flexibles y extensibles, no hay muchos ejemplos de estas propiedades en las API predeterminadas [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ). Puede establecer el enlace para que tenga un valor predeterminado bidireccionales para las propiedades que unen los comportamientos de un control entre sus<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> partes del componente (es un ejemplo) o donde el enlace bidireccional es el escenario habitual y esperado<xref:System.Windows.Controls.TextBox.Text%2A> para los usuarios (es un ejemplo). Cambiar los metadatos relacionados con el enlace de datos afecta únicamente al valor predeterminado; en una base por enlace siempre se puede cambiar el valor predeterminado. Para obtener más información sobre los modos de enlace y el enlace en general, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
- Notificar si las aplicaciones o los servicios que admiten el registro en diario (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>) deben registrar las propiedades. Para los elementos generales, la inclusión en el diario no está habilitada de manera predeterminada, pero se habilita de forma selectiva para determinados controles de entrada de usuario. Esta propiedad está pensada para que la lean los servicios de registro en diario, incluida la implementación de registro en diario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, normalmente, se establece en los controles de usuario, como las selecciones del usuario en las listas que deben conservarse en los pasos de navegación. Para obtener información sobre el diario, consulte [Información general sobre navegación](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Leer FrameworkPropertyMetadata  
 Cada una de las propiedades vinculadas anteriormente son las propiedades específicas <xref:System.Windows.FrameworkPropertyMetadata> que agrega a su clase <xref:System.Windows.UIPropertyMetadata>base inmediata. Cada una de estas propiedades será `false` de manera predeterminada. Una solicitud de metadatos para una propiedad en la que conocer el valor de estas propiedades es importante debe intentar convertir los <xref:System.Windows.FrameworkPropertyMetadata>metadatos devueltos a y, a continuación, comprobar los valores de las propiedades individuales según sea necesario.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Especificar los metadatos  
 Al crear una nueva instancia de metadatos con el fin de aplicar los metadatos a un nuevo registro de propiedades de dependencia, tiene la opción de elegir qué clase <xref:System.Windows.PropertyMetadata> de metadatos se va a <xref:System.Windows.FrameworkPropertyMetadata>usar: la base o alguna clase derivada como. En general, debe usar <xref:System.Windows.FrameworkPropertyMetadata>, especialmente si la propiedad tiene alguna interacción con el sistema de propiedades y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funciones como el diseño y el enlace de datos. Otra opción para escenarios más sofisticados es derivar <xref:System.Windows.FrameworkPropertyMetadata> de para crear su propia clase de informes de metadatos con información adicional incluida en sus miembros. O bien, puede <xref:System.Windows.PropertyMetadata> usar <xref:System.Windows.UIPropertyMetadata> o para comunicar el grado de compatibilidad con las características de la implementación.  
  
 En el caso de<xref:System.Windows.DependencyProperty.AddOwner%2A> las <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> propiedades existentes (o llamar a), siempre debe invalidar con el tipo de metadatos utilizado por el registro original.  
  
 Si va a crear una <xref:System.Windows.FrameworkPropertyMetadata> instancia de, hay dos maneras de rellenar los metadatos con valores para las propiedades específicas que comunican las características de la propiedad de marco de trabajo:  
  
1. Use la <xref:System.Windows.FrameworkPropertyMetadata> firma del constructor que permite `flags` un parámetro. Este parámetro se debe rellenar con todos los valores combinados <xref:System.Windows.FrameworkPropertyMetadataOptions> deseados de las marcas de enumeración.  
  
2. Use una de las firmas sin un `flags` parámetro y, a continuación, establezca cada propiedad booleana `true` de <xref:System.Windows.FrameworkPropertyMetadata> informes en para cada cambio de característica deseado. Si lo hace, debe establecer estas propiedades antes de que se construya cualquier elemento con esta propiedad de dependencia; las propiedades booleanas son de lectura y escritura para permitir este comportamiento de evitar el parámetro `flags` y, aun así, rellenar los metadatos, pero los metadatos deben sellarse herméticamente antes del uso de la propiedad. Por lo tanto, intentar establecer las propiedades después de haber solicitado los metadatos será una operación no válida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Comportamiento de combinación de los metadatos de las propiedades de marco de trabajo  
 Cuando se invalidan los metadatos de las propiedades de marco de trabajo, las distintas características de los metadatos se combinan o reemplazan.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>se combina. Si agrega un nuevo <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se promueve como referencia del antecesor más cercano que lo especificó en los metadatos.  
  
- El comportamiento real del sistema de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> propiedades para es que las implementaciones de todos los propietarios de metadatos de la jerarquía se retienen y se agregan a una tabla, con orden de ejecución por el sistema de propiedades que las devoluciones de llamada de la clase más derivada son. se invoca en primer lugar. Las devoluciones de llamada heredadas se ejecutan solo una vez, y se cuentan como propiedad de la clase que las colocó en los metadatos.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>se ha reemplazado. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.DefaultValue%2A> proviene del antecesor más cercano que lo especificó en los metadatos.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>las implementaciones se han reemplazado. Si agrega un nuevo <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se promueve como referencia del antecesor más cercano que lo especificó en los metadatos.  
  
- El comportamiento del sistema <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> de propiedades es que solo se invoca en los metadatos inmediatos. No se conserva ninguna <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> referencia a otras implementaciones en la jerarquía.  
  
- Las marcas de <xref:System.Windows.FrameworkPropertyMetadataOptions> enumeración se combinan como una operación OR bit a bit.  Si especifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, no se sobrescriben las opciones originales.  Para cambiar una opción, establezca la propiedad correspondiente en <xref:System.Windows.FrameworkPropertyMetadata>. Por ejemplo, si el objeto <xref:System.Windows.FrameworkPropertyMetadata> original establece la <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> marca, <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> puede cambiarla estableciendo en `false`.  
  
 Implementa <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>este comportamiento y se puede invalidar en clases de metadatos derivadas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
