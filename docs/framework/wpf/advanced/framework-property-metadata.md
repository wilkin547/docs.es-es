---
title: Metadatos de las propiedades de marco de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 3e40dfbcbe88f424337ee5a32fb3e3aaaddd68d0
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460464"
---
# <a name="framework-property-metadata"></a>Metadatos de las propiedades de marco de trabajo
Las opciones de metadatos de propiedad de marco de trabajo se notifican para las propiedades de los elementos de objeto que se consideran presentes en el nivel de marco de trabajo de WPF en la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En general, la designación de nivel de marco de WPF implica que las características como la representación, el enlace de datos y las mejoras del sistema de propiedades se controlan mediante las API de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y los ejecutables. Estos sistemas consultan los metadatos de las propiedades de marco de trabajo para determinar las particularidades específicas de las características de las propiedades de un elemento en particular.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). También debería haber leído [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Información que comunican los metadatos de las propiedades de marco de trabajo  
 Los metadatos de las propiedades de marco de trabajo se pueden dividir en las siguientes categorías:  
  
- Propiedades de diseño de informes que afectan a un elemento (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). Puede establecer estas marcas en los metadatos si la propiedad afecta a esos aspectos respectivos, y también está implementando el <xref:System.Windows.FrameworkElement.MeasureOverride%2A> / <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos de la clase para proporcionar un comportamiento de representación específico e información al sistema de diseño. Normalmente, una implementación tal comprobaría las invalidaciones de propiedad en las propiedades de dependencia donde cualquiera de estas propiedades de diseño fuese verdadera en los metadatos de las propiedades, y solo esas invalidaciones tendrían que solicitar un nuevo paso de diseño.  
  
- Propiedades de diseño de informes que afectan al elemento primario de un elemento (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Algunos ejemplos en los que se establecen estas marcas de forma predeterminada son <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> y <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>Operador De manera predeterminada, las propiedades de dependencia no heredan los valores. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> permite que la ruta de herencia también viaje a un árbol visual, que es necesario para algunos escenarios de composición de controles.  
  
    > [!NOTE]
    > El término "hereda" en el contexto de los valores de propiedades significa algo específico para las propiedades de dependencia; significa que los elementos secundarios pueden heredar el valor real de la propiedad de dependencia de los elementos primarios debido a una capacidad de nivel de marco de trabajo de WPF del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. No tiene nada que ver directamente con la herencia de tipos y miembros de código administrado a través de tipos derivados. Para obtener información detallada, consulte [Herencia de valores de propiedad](property-value-inheritance.md).  
  
- Características de enlace de datos de informes (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). De manera predeterminada, las propiedades de dependencia en el marco de trabajo admiten el enlace de datos, con un comportamiento de enlace unidireccional. Puede deshabilitar el enlace de datos si no hay ningún escenario para ello (porque están diseñados para ser flexibles y extensibles, no hay muchos ejemplos de estas propiedades en las API de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminadas). Puede establecer el enlace para que tenga un valor predeterminado bidireccionales para las propiedades que unen los comportamientos de un control entre sus partes del componente (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> es un ejemplo) o donde el enlace bidireccional es el escenario habitual y esperado para los usuarios (<xref:System.Windows.Controls.TextBox.Text%2A> es un ejemplo). Cambiar los metadatos relacionados con el enlace de datos afecta únicamente al valor predeterminado; en una base por enlace siempre se puede cambiar el valor predeterminado. Para obtener más información sobre los modos de enlace y el enlace en general, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Notificar si las aplicaciones o los servicios que admiten el registro en diario (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>) deben registrar las propiedades. Para los elementos generales, la inclusión en el diario no está habilitada de manera predeterminada, pero se habilita de forma selectiva para determinados controles de entrada de usuario. Esta propiedad está pensada para que la lean los servicios de registro en diario, incluida la implementación de registro en diario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, normalmente, se establece en los controles de usuario, como las selecciones del usuario en las listas que deben conservarse en los pasos de navegación. Para obtener información sobre el diario, consulte [Información general sobre navegación](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Leer FrameworkPropertyMetadata  
 Cada una de las propiedades vinculadas anteriormente son las propiedades específicas que el <xref:System.Windows.FrameworkPropertyMetadata> agrega a su clase base inmediata <xref:System.Windows.UIPropertyMetadata>. Cada una de estas propiedades será `false` de manera predeterminada. Una solicitud de metadatos para una propiedad en la que conocer el valor de estas propiedades es importante debe intentar convertir los metadatos devueltos en <xref:System.Windows.FrameworkPropertyMetadata>y, a continuación, comprobar los valores de las propiedades individuales según sea necesario.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Especificar los metadatos  
 Al crear una nueva instancia de metadatos para aplicar los metadatos a un nuevo registro de propiedades de dependencia, tiene la opción de elegir qué clase de metadatos se va a usar: el <xref:System.Windows.PropertyMetadata> base o alguna clase derivada como <xref:System.Windows.FrameworkPropertyMetadata>. En general, debe usar <xref:System.Windows.FrameworkPropertyMetadata>, especialmente si la propiedad tiene alguna interacción con el sistema de propiedades y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funciones como el diseño y el enlace de datos. Otra opción para escenarios más sofisticados es derivar de <xref:System.Windows.FrameworkPropertyMetadata> para crear su propia clase de informes de metadatos con información adicional que se lleva a cabo en sus miembros. O bien, puede usar <xref:System.Windows.PropertyMetadata> o <xref:System.Windows.UIPropertyMetadata> para comunicar el grado de compatibilidad con las características de la implementación.  
  
 En el caso de las propiedades existentes (<xref:System.Windows.DependencyProperty.AddOwner%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> llamada), siempre debe invalidar con el tipo de metadatos utilizado por el registro original.  
  
 Si va a crear una instancia de <xref:System.Windows.FrameworkPropertyMetadata>, hay dos maneras de rellenar los metadatos con valores para las propiedades específicas que comunican las características de la propiedad de marco de trabajo:  
  
1. Use la firma del constructor <xref:System.Windows.FrameworkPropertyMetadata> que permite un parámetro `flags`. Este parámetro se debe rellenar con todos los valores combinados deseados de las marcas de enumeración <xref:System.Windows.FrameworkPropertyMetadataOptions>.  
  
2. Use una de las firmas sin un parámetro de `flags` y, a continuación, establezca cada propiedad booleana de informe en <xref:System.Windows.FrameworkPropertyMetadata> en `true` para cada cambio de característica deseado. Si lo hace, debe establecer estas propiedades antes de que se construya cualquier elemento con esta propiedad de dependencia; las propiedades booleanas son de lectura y escritura para permitir este comportamiento de evitar el parámetro `flags` y, aun así, rellenar los metadatos, pero los metadatos deben sellarse herméticamente antes del uso de la propiedad. Por lo tanto, intentar establecer las propiedades después de haber solicitado los metadatos será una operación no válida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Comportamiento de combinación de los metadatos de las propiedades de marco de trabajo  
 Cuando se invalidan los metadatos de las propiedades de marco de trabajo, las distintas características de los metadatos se combinan o reemplazan.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se combina. Si agrega una nueva <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se promueve como referencia del antecesor más próximo que lo especificó en los metadatos.  
  
- El comportamiento real del sistema de propiedades para <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> es que las implementaciones de todos los propietarios de metadatos de la jerarquía se retienen y se agregan a una tabla, con el orden de ejecución por parte del sistema de propiedades de que se invocan las devoluciones de llamada de la clase más derivada. lugar. Las devoluciones de llamada heredadas se ejecutan solo una vez, y se cuentan como propiedad de la clase que las colocó en los metadatos.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> se reemplaza. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.DefaultValue%2A> procede del antecesor más cercano que lo especificó en los metadatos.  
  
- se reemplazan las implementaciones de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>. Si agrega una nueva <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se promueve como referencia del antecesor más próximo que lo especificó en los metadatos.  
  
- El comportamiento del sistema de propiedades es que solo se invoca el <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en los metadatos inmediatos. No se conserva ninguna referencia a otras implementaciones de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la jerarquía.  
  
- Las marcas de <xref:System.Windows.FrameworkPropertyMetadataOptions> enumeración se combinan como una operación OR bit a bit.  Si especifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, no se sobrescriben las opciones originales.  Para cambiar una opción, establezca la propiedad correspondiente en <xref:System.Windows.FrameworkPropertyMetadata>. Por ejemplo, si el objeto <xref:System.Windows.FrameworkPropertyMetadata> original establece la marca <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType>, puede cambiarla estableciendo <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> en `false`.  
  
 Este comportamiento se implementa mediante <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>y se puede invalidar en clases de metadatos derivadas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
