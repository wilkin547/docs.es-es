---
title: Metadatos de las propiedades de marco de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: b6bacf6f0c27b123d36f17510d84e5ef5e2cf122
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108711"
---
# <a name="framework-property-metadata"></a>Metadatos de las propiedades de marco de trabajo
Las opciones de metadatos de propiedad de marco de trabajo se notifican para las propiedades de los elementos de objeto que se consideran presentes en el nivel de marco de trabajo de WPF en la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En general, la designación de nivel de marco de trabajo de WPF implica que las características, como la representación, el enlace de datos y los refinamientos del sistema de propiedades se controlen mediante las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] y los ejecutables de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Estos sistemas consultan los metadatos de las propiedades de marco de trabajo para determinar las particularidades específicas de las características de las propiedades de un elemento en particular.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). También debería haber leído [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>Información que comunican los metadatos de las propiedades de marco de trabajo  
 Los metadatos de las propiedades de marco de trabajo se pueden dividir en las siguientes categorías:  
  
-   Las propiedades de diseño que afectan a un elemento (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). Puede establecer estas marcas en los metadatos si la propiedad afecta a esos aspectos respectivos, y también está implementando el <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> métodos en la clase para proporcionar información al diseño y el comportamiento de representación específica sistema. Normalmente, una implementación tal comprobaría las invalidaciones de propiedad en las propiedades de dependencia donde cualquiera de estas propiedades de diseño fuese verdadera en los metadatos de las propiedades, y solo esas invalidaciones tendrían que solicitar un nuevo paso de diseño.  
  
-   Las propiedades de diseño que afectan al elemento primario de un elemento (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). Algunos ejemplos donde se establecen estas marcas de forma predeterminada son <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> y <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>.  
  
-   <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. De manera predeterminada, las propiedades de dependencia no heredan los valores. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> permite que la ruta de herencia también recorrer un árbol visual, que es necesario para algunos escenarios de composición de control.  
  
    > [!NOTE]
    >  El término "hereda" en el contexto de los valores de propiedades significa algo específico para las propiedades de dependencia; significa que los elementos secundarios pueden heredar el valor real de la propiedad de dependencia de los elementos primarios debido a una capacidad de nivel de marco de trabajo de WPF del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. No tiene nada que ver directamente con la herencia de tipos y miembros de código administrado a través de tipos derivados. Para obtener información detallada, consulte [Herencia de valores de propiedad](property-value-inheritance.md).  
  
-   Las características de enlace de datos de informes (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). De manera predeterminada, las propiedades de dependencia en el marco de trabajo admiten el enlace de datos, con un comportamiento de enlace unidireccional. Puede deshabilitar el enlace de datos si no hubiera ningún escenario para ello en absoluto (dado que se han diseñado para ser flexibles y extensibles, no hay muchos ejemplos de estas propiedades en las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] predeterminadas de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]). Puede establecer el enlace para tener un valor predeterminado bidireccional para las propiedades que conectan entre sí los comportamientos de un control entre sus partes constitutivas (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> es un ejemplo) o donde el enlace bidireccional es el escenario común y esperado para los usuarios (<xref:System.Windows.Controls.TextBox.Text%2A> es un ejemplo). Cambiar los metadatos relacionados con el enlace de datos afecta únicamente al valor predeterminado; en una base por enlace siempre se puede cambiar el valor predeterminado. Para obtener más información sobre los modos de enlace y el enlace en general, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
-   Informar de si las propiedades deben ser aplicaciones o servicios que admiten el registro en diario (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). Para los elementos generales, la inclusión en el diario no está habilitada de manera predeterminada, pero se habilita de forma selectiva para determinados controles de entrada de usuario. Esta propiedad está pensada para que la lean los servicios de registro en diario, incluida la implementación de registro en diario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, normalmente, se establece en los controles de usuario, como las selecciones del usuario en las listas que deben conservarse en los pasos de navegación. Para obtener información sobre el diario, consulte [Información general sobre navegación](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>Leer FrameworkPropertyMetadata  
 Cada una de las propiedades vinculadas anteriormente son propiedades específicas que la <xref:System.Windows.FrameworkPropertyMetadata> agrega a su clase base inmediata <xref:System.Windows.UIPropertyMetadata>. Cada una de estas propiedades será `false` de manera predeterminada. Una solicitud de metadatos para una propiedad donde es importante conocer el valor de estas propiedades debe intentar convertir los metadatos devueltos a <xref:System.Windows.FrameworkPropertyMetadata>y, a continuación, compruebe los valores de las propiedades individuales según sea necesario.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>Especificar los metadatos  
 Cuando se crea una nueva instancia de metadatos para fines de aplicar metadatos a un nuevo registro de la propiedad de dependencia, tiene la opción de qué clase de metadatos para usar: la base de <xref:System.Windows.PropertyMetadata> o a una clase derivada, como <xref:System.Windows.FrameworkPropertyMetadata>. En general, debe usar <xref:System.Windows.FrameworkPropertyMetadata>, especialmente si la propiedad tiene cualquier interacción con el sistema de propiedades y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funciones como el diseño y el enlace de datos. Otra opción para escenarios más sofisticados consiste en derivar <xref:System.Windows.FrameworkPropertyMetadata> para crear sus propios metadatos de clase con información adicional de informes lleva en sus miembros. O bien puede usar <xref:System.Windows.PropertyMetadata> o <xref:System.Windows.UIPropertyMetadata> para comunicar el grado de compatibilidad con las características de su implementación.  
  
 Para las propiedades existentes (<xref:System.Windows.DependencyProperty.AddOwner%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> llamar), debe invalidar siempre con el tipo de metadatos utilizado por el registro original.  
  
 Si está creando un <xref:System.Windows.FrameworkPropertyMetadata> de la instancia, hay dos maneras de rellenar esos metadatos con los valores de las propiedades específicas que se comunican las características de la propiedad de marco de trabajo:  
  
1.  Use la <xref:System.Windows.FrameworkPropertyMetadata> firma del constructor que permite un `flags` parámetro. Este parámetro debe rellenarse con deseado todos los valores combinados de la <xref:System.Windows.FrameworkPropertyMetadataOptions> marcas de enumeración.  
  
2.  Use una de las firmas sin un `flags` parámetro y, a continuación, establezca cada propiedad booleana de comunicación en <xref:System.Windows.FrameworkPropertyMetadata> a `true` para cada cambio de característica que desee. Si lo hace, debe establecer estas propiedades antes de que se construya cualquier elemento con esta propiedad de dependencia; las propiedades booleanas son de lectura y escritura para permitir este comportamiento de evitar el parámetro `flags` y, aun así, rellenar los metadatos, pero los metadatos deben sellarse herméticamente antes del uso de la propiedad. Por lo tanto, intentar establecer las propiedades después de haber solicitado los metadatos será una operación no válida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>Comportamiento de combinación de los metadatos de las propiedades de marco de trabajo  
 Cuando se invalidan los metadatos de las propiedades de marco de trabajo, las distintas características de los metadatos se combinan o reemplazan.  
  
-   <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se combina. Si agrega un nuevo <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se promueve como referencia del antecesor más próximo que se haya especificado en los metadatos.  
  
-   El comportamiento del sistema de propiedad real para <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> es que las implementaciones para todos los propietarios de metadatos de la jerarquía se conservan y se agregan a una tabla, con el orden de ejecución en el sistema de propiedades que las devoluciones de llamada de la clase derivada más profundamente son se invoca en primer lugar. Las devoluciones de llamada heredadas se ejecutan solo una vez, y se cuentan como propiedad de la clase que las colocó en los metadatos.  
  
-   <xref:System.Windows.PropertyMetadata.DefaultValue%2A> se ha reemplazado. Si no especifica un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.DefaultValue%2A> proviene del antecesor más cercano que se haya especificado en los metadatos.  
  
-   <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se reemplazan las implementaciones. Si agrega un nuevo <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, esa devolución de llamada se almacena en los metadatos. Si no especifica un <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se promueve como referencia del antecesor más próximo que se haya especificado en los metadatos.  
  
-   El comportamiento del sistema de propiedades es que sólo el <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se invoca en los metadatos inmediatos. No hay referencias a otras <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se conservan las implementaciones en la jerarquía.  
  
-   Las marcas de <xref:System.Windows.FrameworkPropertyMetadataOptions> enumeración se combinan como una operación OR bit a bit.  Si especifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, no se sobrescriben las opciones originales.  Para cambiar una opción, establezca la propiedad correspondiente en <xref:System.Windows.FrameworkPropertyMetadata>. Por ejemplo, si la versión original <xref:System.Windows.FrameworkPropertyMetadata> conjuntos de objetos la <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> marca, se puede cambiar estableciendo <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> a `false`.  
  
 Este comportamiento se implementa mediante <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>y se puede invalidar en clases de metadatos derivadas.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
