---
title: Metadatos de las propiedades de marco de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 8fb6e1b4cf6aed9454e9e9f1a77277d2f3611ca8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186655"
---
# <a name="framework-property-metadata"></a>Metadatos de las propiedades de marco de trabajo
Las opciones de metadatos de propiedad de marco de trabajo se notifican para las propiedades de los elementos de objeto que se consideran presentes en el nivel de marco de trabajo de WPF en la arquitectura de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. En general, la designación de nivel de marco de WPFWPF implica que las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características como la representación, el enlace de datos y los refinamientos del sistema de propiedades se controlan mediante las API de presentación y los ejecutables. Estos sistemas consultan los metadatos de las propiedades de marco de trabajo para determinar las particularidades específicas de las características de las propiedades de un elemento en particular.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](dependency-properties-overview.md). También debería haber leído [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>
## <a name="what-is-communicated-by-framework-property-metadata"></a>Información que comunican los metadatos de las propiedades de marco de trabajo  
 Los metadatos de las propiedades de marco de trabajo se pueden dividir en las siguientes categorías:  
  
- Notificación de propiedades de<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>diseño <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>que afectan a un elemento ( , , ). Puede establecer estas marcas en metadatos si la propiedad afecta a <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> esos aspectos respectivos y también está implementando los métodos de la clase para proporcionar información y comportamiento de representación específicos al sistema de diseño. Normalmente, una implementación tal comprobaría las invalidaciones de propiedad en las propiedades de dependencia donde cualquiera de estas propiedades de diseño fuese verdadera en los metadatos de las propiedades, y solo esas invalidaciones tendrían que solicitar un nuevo paso de diseño.  
  
- Notificación de propiedades de diseño que<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A> <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>afectan al elemento primario de un elemento ( , ). Algunos ejemplos en los que <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> estas <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>marcas se establecen de forma predeterminada son y .  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. De manera predeterminada, las propiedades de dependencia no heredan los valores. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A>permite que la vía de la herencia también viaje a un árbol visual, que es necesario para algunos escenarios de composición de control.  
  
    > [!NOTE]
    > El término "hereda" en el contexto de los valores de propiedades significa algo específico para las propiedades de dependencia; significa que los elementos secundarios pueden heredar el valor real de la propiedad de dependencia de los elementos primarios debido a una capacidad de nivel de marco de trabajo de WPF del sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. No tiene nada que ver directamente con la herencia de tipos y miembros de código administrado a través de tipos derivados. Para obtener más información, vea Herencia de valor de [propiedad](property-value-inheritance.md).  
  
- Características de enlace<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A> <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>de datos de informes ( , ). De manera predeterminada, las propiedades de dependencia en el marco de trabajo admiten el enlace de datos, con un comportamiento de enlace unidireccional. Puede deshabilitar el enlace de datos si no hubiera ningún escenario para él (porque están diseñados para ser flexibles y extensibles, no hay muchos ejemplos de estas propiedades en las API predeterminadas). [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Puede establecer el enlace para tener un valor predeterminado bidireccional para las propiedades que unen los comportamientos de un control entre sus partes de componentes (es<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> un ejemplo) o donde el enlace bidireccional es el escenario común y esperado para los usuarios (<xref:System.Windows.Controls.TextBox.Text%2A> es un ejemplo). Cambiar los metadatos relacionados con el enlace de datos afecta únicamente al valor predeterminado; en una base por enlace siempre se puede cambiar el valor predeterminado. Para obtener más información sobre los modos de enlace y el enlace en general, consulte [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).  
  
- Informe de si las aplicaciones o los servicios<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>que admiten el registro en diario ( ). Para los elementos generales, la inclusión en el diario no está habilitada de manera predeterminada, pero se habilita de forma selectiva para determinados controles de entrada de usuario. Esta propiedad está pensada para que la lean los servicios de registro en diario, incluida la implementación de registro en diario de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y, normalmente, se establece en los controles de usuario, como las selecciones del usuario en las listas que deben conservarse en los pasos de navegación. Para obtener información sobre el diario, consulte [Información general sobre navegación](../app-development/navigation-overview.md).  
  
<a name="Reading_FrameworkPropertyMetadata"></a>
## <a name="reading-frameworkpropertymetadata"></a>Leer FrameworkPropertyMetadata  
 Cada una de las propiedades vinculadas <xref:System.Windows.FrameworkPropertyMetadata> anteriormente son las <xref:System.Windows.UIPropertyMetadata>propiedades específicas que se agrega a su clase base inmediata. Cada una de estas propiedades será `false` de manera predeterminada. Una solicitud de metadatos para una propiedad donde es importante conocer el <xref:System.Windows.FrameworkPropertyMetadata>valor de estas propiedades debe intentar convertir los metadatos devueltos en y, a continuación, comprobar los valores de las propiedades individuales según sea necesario.  
  
<a name="Specifying_Metadata"></a>
## <a name="specifying-metadata"></a>Especificar los metadatos  
 Al crear una nueva instancia de metadatos para aplicar metadatos a un nuevo registro de propiedad de <xref:System.Windows.PropertyMetadata> dependencia, tiene la <xref:System.Windows.FrameworkPropertyMetadata>opción de elegir qué clase de metadatos usar: la base o alguna clase derivada como . En general, debe <xref:System.Windows.FrameworkPropertyMetadata>usar , especialmente si su propiedad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene alguna interacción con el sistema de propiedades y funciones como el diseño y el enlace de datos. Otra opción para escenarios más <xref:System.Windows.FrameworkPropertyMetadata> sofisticados es derivar de crear su propia clase de informes de metadatos con información adicional llevada en sus miembros. O puede <xref:System.Windows.PropertyMetadata> usar <xref:System.Windows.UIPropertyMetadata> o para comunicar el grado de compatibilidad con las características de la implementación.  
  
 Para las<xref:System.Windows.DependencyProperty.AddOwner%2A> propiedades <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> existentes (o llamada), siempre debe invalidar con el tipo de metadatos utilizado por el registro original.  
  
 Si va a <xref:System.Windows.FrameworkPropertyMetadata> crear una instancia, hay dos maneras de rellenar esos metadatos con valores para las propiedades específicas que comunican las características de propiedad del marco de trabajo:  
  
1. Utilice <xref:System.Windows.FrameworkPropertyMetadata> la firma del `flags` constructor que permite un parámetro. Este parámetro debe rellenarse con todos <xref:System.Windows.FrameworkPropertyMetadataOptions> los valores combinados deseados de los indicadores de enumeración.  
  
2. Utilice una de las `flags` firmas sin un parámetro y, `true` a continuación, establezca cada propiedad booleana de informes en <xref:System.Windows.FrameworkPropertyMetadata> cada cambio de característica deseado. Si lo hace, debe establecer estas propiedades antes de que se construya cualquier elemento con esta propiedad de dependencia; las propiedades booleanas son de lectura y escritura para permitir este comportamiento de evitar el parámetro `flags` y, aun así, rellenar los metadatos, pero los metadatos deben sellarse herméticamente antes del uso de la propiedad. Por lo tanto, intentar establecer las propiedades después de haber solicitado los metadatos será una operación no válida.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>
## <a name="framework-property-metadata-merge-behavior"></a>Comportamiento de combinación de los metadatos de las propiedades de marco de trabajo  
 Cuando se invalidan los metadatos de las propiedades de marco de trabajo, las distintas características de los metadatos se combinan o reemplazan.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>se fusiona. Si agrega un <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>nuevo , esa devolución de llamada se almacena en los metadatos. Si no especifica <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> a en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> se promueve como una referencia desde el antecesor más cercano que lo especificó en los metadatos.  
  
- El comportamiento real <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> del sistema de propiedades es que las implementaciones para todos los propietarios de metadatos de la jerarquía se conservan y se agregan a una tabla, con el orden de ejecución por parte del sistema de propiedades siendo que las devoluciones de llamada de la clase más profundamente derivada se invocan primero. Las devoluciones de llamada heredadas se ejecutan solo una vez, y se cuentan como propiedad de la clase que las colocó en los metadatos.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A>se sustituye. Si no especifica <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> a en la invalidación, el valor del <xref:System.Windows.PropertyMetadata.DefaultValue%2A> antecesor más cercano que lo especificó en los metadatos.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>se sustituyen las implementaciones. Si agrega un <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>nuevo , esa devolución de llamada se almacena en los metadatos. Si no especifica <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> a en la invalidación, el valor de <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> se promueve como una referencia desde el antecesor más cercano que lo especificó en los metadatos.  
  
- El comportamiento del sistema <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> de propiedades es que solo se invocan los metadatos inmediatos. No se <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> conservan las referencias a otras implementaciones de la jerarquía.  
  
- Los indicadores de <xref:System.Windows.FrameworkPropertyMetadataOptions> enumeración se combinan como una operación OR bit a bit.  Si especifica <xref:System.Windows.FrameworkPropertyMetadataOptions>, las opciones originales no se sobrescriben.  Para cambiar una opción, establezca <xref:System.Windows.FrameworkPropertyMetadata>la propiedad correspondiente en . Por ejemplo, si <xref:System.Windows.FrameworkPropertyMetadata> el <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> objeto original establece la <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> marca, puede cambiarla estableciendo `false`en .  
  
 Este comportamiento se <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>implementa mediante , y se puede invalidar en clases de metadatos derivadas.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
