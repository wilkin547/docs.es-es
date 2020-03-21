---
title: Herencia de valores de propiedad
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [WPF], property values
- value inheritance [WPF]
- properties [WPF], value inheritance
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
ms.openlocfilehash: b63f307d9edffd14315d383d8e06419fa141aee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187188"
---
# <a name="property-value-inheritance"></a>Herencia de valores de propiedad
La herencia de valores de propiedad es una característica del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. La herencia de valores de propiedad permite que los elementos secundarios de un árbol de elementos obtengan el valor de una propiedad determinada de los elementos principales y que hereden ese valor tal como se estableció en cualquier otro lugar del elemento principal más cercano. Es posible que el elemento principal también haya obtenido su valor a través de la herencia de valores de propiedad, por lo que el sistema se repite potencialmente hasta la raíz de la página. La herencia de valores de propiedad no es el comportamiento del sistema de propiedades predeterminado: es necesario establecer una propiedad con un valor de metadatos concreto para que inicie la herencia de valores de propiedad en elementos secundarios.  

<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>
## <a name="property-value-inheritance-is-containment-inheritance"></a>La herencia de valores de propiedad es la herencia de contención  
 "Herencia" como término aquí no es exactamente el mismo concepto que la herencia en el contexto de programación orientada a objetos generales y tipos, donde las clases derivadas heredan las definiciones de miembros de sus clases base. Ese significado de herencia también está activo en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: las propiedades definidas en varias clases base se exponen como atributos para clases [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] derivadas cuando se usan como elementos y se exponen como miembros para código. La herencia de valores de propiedad trata especialmente acerca de cómo los valores de propiedad se pueden heredar de un elemento a otro basándose en las relaciones entre elementos primarios y secundarios de un árbol de elementos. Este árbol de elementos es visible directamente al anidar elementos dentro de otros elementos cuando se definen aplicaciones en el marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Los árboles de objetos también pueden crearse mediante programación si se agregan objetos a colecciones designadas de otros objetos. La herencia de valores de propiedad funciona del mismo modo en el árbol terminado en tiempo de ejecución.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>
## <a name="practical-applications-of-property-value-inheritance"></a>Aplicaciones prácticas de la herencia de valores de propiedad  
 Las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API incluyen varias propiedades que tienen habilitada la herencia de propiedades. Normalmente, el escenario en estos casos es que implican una propiedad donde es apropiado que se establezca la propiedad una sola vez por página, pero donde esa propiedad también es un miembro de una de las clases de elementos base y, por tanto, también existirá en la mayoría de los elementos secundarios. Por ejemplo, <xref:System.Windows.FrameworkElement.FlowDirection%2A> la propiedad controla qué dirección fluyó el contenido debe presentarse y organizarse en la página. Normalmente, quiere que el concepto de flujo de texto se controle de forma coherente en todos los elementos secundarios. Si el usuario o una acción del entorno restableciera la dirección de flujo por alguna razón en algún nivel del árbol de elementos, normalmente, debería restablecerse en todo el árbol. Cuando <xref:System.Windows.FrameworkElement.FlowDirection%2A> se hace que la propiedad herede, el valor solo debe establecerse o restablecerse una vez en el nivel del árbol de elementos que abarca las necesidades de presentación de cada página de la aplicación. Incluso el valor predeterminado inicial se heredará de esta manera. El modelo de herencia de valor de propiedad aún permite que elementos individuales restablezcan el valor para los pocos casos en los que tener una combinación de direcciones de flujo es deliberado.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>
## <a name="making-a-custom-property-inheritable"></a>Hacer heredable una propiedad personalizada  
 Al cambiar los metadatos de una propiedad personalizada, también puede hacer que sus propias propiedades personalizadas sean heredables. Sin embargo, tenga en cuenta que designar una propiedad como heredable tiene algunas consideraciones de rendimiento. En casos donde esa propiedad no tiene ningún valor local establecido o ningún valor obtenido a través de estilos, plantillas o enlaces de datos, una propiedad heredable proporciona sus valores de propiedad asignados a todos los elementos secundarios del árbol lógico.  
  
 Para que una propiedad participe en la herencia de valores, cree una propiedad asociada personalizada, tal como se describe en [Registrar una propiedad asociada](how-to-register-an-attached-property.md). Registre la propiedad<xref:System.Windows.FrameworkPropertyMetadata>con metadatos ( ) y especifique la opción "Inherits" en la configuración de opciones dentro de esos metadatos. Asegúrese también de que la propiedad tenga un valor predeterminado establecido, porque ahora se heredará ese valor. Aunque registró la propiedad como asociada, es posible que también quiera crear una propiedad "wrapper" para obtener o establecer acceso al tipo de propietario, del mismo modo que para una propiedad de dependencia "nonattached". Después de hacerlo, la propiedad heredable se puede establecer mediante el contenedor de propiedades directas en el tipo <xref:System.Windows.DependencyObject>de propietario o tipos derivados, o se puede establecer mediante la sintaxis de propiedad adjunta en cualquier archivo .  
  
 Las propiedades adjuntas son conceptualmente similares a las propiedades globales; puede comprobar el valor <xref:System.Windows.DependencyObject> en cualquier y obtener un resultado válido. El escenario típico de las propiedades adjuntas es establecer valores de propiedad en elementos secundarios y ese escenario es más eficaz<xref:System.Windows.DependencyObject>si la propiedad en cuestión es una propiedad adjunta que siempre está implícitamente presente como una propiedad adjunta en cada elemento ( ) en el árbol.  
  
> [!NOTE]
> Aunque puede parecer que la herencia de valores de propiedad funciona para las propiedades de dependencia que no son asociadas, el comportamiento de la herencia para una propiedad no asociada a través de algunos límites de elementos en el árbol de tiempo de ejecución es indefinido. Utilícelo <xref:System.Windows.DependencyProperty.RegisterAttached%2A> siempre para registrar <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> las propiedades donde especifique en los metadatos.  
  
<a name="InheritanceContext"></a>
## <a name="inheriting-property-values-across-tree-boundaries"></a>Heredar valores de propiedad entre límites de árbol  
 La herencia de propiedades funciona al recorrer un árbol de elementos. Este árbol suele ser paralelo al árbol lógico. Sin embargo, siempre que se incluye un WPFWPF objeto de <xref:System.Windows.Media.Brush>nivel principal en el marcado que define un árbol de elementos, como un , se ha creado un árbol lógico discontinuo. Un árbol lógico verdadero no se <xref:System.Windows.Media.Brush>extiende conceptualmente a través de la , porque el árbol lógico es un concepto de nivel de marco wpfWPF. Puede ver esto reflejado en los resultados <xref:System.Windows.LogicalTreeHelper>cuando se utilizan los métodos de . Sin embargo, la herencia de valores de propiedad puede salvar esta brecha en el árbol lógico y todavía puede pasar valores heredados, <xref:System.Windows.Controls.Frame>siempre y cuando la propiedad heredable se haya registrado como una propiedad adjunta y no se encuentre ningún límite de bloqueo de herencia deliberado (como un ).  
  
## <a name="see-also"></a>Consulte también

- [Metadatos de las propiedades de dependencia](dependency-property-metadata.md)
- [Información general sobre propiedades asociadas](attached-properties-overview.md)
- [Precedencia del valor de la propiedad de dependencia](dependency-property-value-precedence.md)
