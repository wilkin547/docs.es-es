---
title: Atributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459929"
---
# <a name="xshared-attribute"></a>Atributo x:Shared
Cuando se establece en `false`, modifica el comportamiento de recuperación de recursos de WPF para que las solicitudes del recurso con atributos creen una nueva instancia para cada solicitud en lugar de compartir la misma instancia para todas las solicitudes.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Comentarios  
 `x:Shared` se asigna al espacio de nombres XAML del lenguaje XAML y se reconoce como un elemento válido del lenguaje XAML .NET Framework servicios XAML y sus lectores XAML. Sin embargo, las capacidades indicadas de `x:Shared` solo son relevantes para las aplicaciones de WPF y para el analizador XAML de WPF. En WPF, `x:Shared` solo es útil como atributo cuando se aplica a un objeto que existe dentro de un <xref:System.Windows.ResourceDictionary>de WPF. Otros usos no producen excepciones de análisis u otros errores, pero no tienen ningún efecto.  
  
 El significado de `x:Shared` no se especifica en la especificación del lenguaje XAML. Otras implementaciones de XAML, como las que se basan en .NET Framework servicios XAML, no proporcionan necesariamente compatibilidad con el uso compartido de recursos. Estas implementaciones de XAML podrían proporcionar un comportamiento similar en el marco de trabajo compatible que también usa valores `x:Shared`.  
  
 En WPF, la condición de `x:Shared` predeterminada para los recursos es `true`. Esta condición significa que cualquier solicitud de recurso determinada siempre devuelve la misma instancia.  
  
 Modificar un objeto que se devuelve a través de una API de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A>o modificar un objeto directamente dentro de un <xref:System.Windows.ResourceDictionary>, cambia el recurso original. Si las referencias a ese recurso eran referencias de recursos dinámicos, los consumidores de ese recurso obtienen el recurso modificado.  
  
 Si las referencias al recurso eran referencias de recursos estáticos, los cambios en el recurso después de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tiempo de procesamiento son irrelevantes. Para obtener más información sobre las referencias de recursos estáticos y dinámicos, vea [recursos XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
 La especificación explícita de `x:Shared="true"` se realiza con poca frecuencia, porque ya es el valor predeterminado. No hay ningún equivalente de código directo para `x:Shared` en el modelo de objetos de WPF; solo se puede especificar en un uso de XAML y debe procesarse mediante el comportamiento predeterminado de WPF o en un flujo de nodo XAML intermedio en la ruta de acceso de carga, si se procesa mediante .NET Framework servicios XAML y sus lectores XAML.  
  
 Un escenario para `x:Shared="false"` es si define un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> clase derivada como un recurso y, a continuación, introduce el recurso de elemento en un modelo de contenido. `x:Shared="false"` permite que un recurso de elemento se introduzca varias veces en la misma colección (por ejemplo, un <xref:System.Windows.Controls.UIElementCollection>). Sin `x:Shared="false"` esto no es válido porque la colección exige la unicidad de su contenido. Sin embargo, el comportamiento de `x:Shared="false"` crea otra instancia idéntica del recurso en lugar de devolver la misma instancia.  
  
 Otro escenario para `x:Shared="false"` es si usa un recurso <xref:System.Windows.Freezable> para los valores de animación pero desea modificar el recurso por animación.  
  
 El control de cadenas de `false` no distingue entre mayúsculas y minúsculas.  
  
 En WPF, `x:Shared` solo es válido en las siguientes condiciones:  
  
- Se debe compilar el <xref:System.Windows.ResourceDictionary> que contiene los elementos con `x:Shared`. El <xref:System.Windows.ResourceDictionary> no puede estar dentro de un código XAML dinámico ni usarse para los temas.  
  
- El <xref:System.Windows.ResourceDictionary> que contiene los elementos no debe estar anidado dentro de otro <xref:System.Windows.ResourceDictionary>. Por ejemplo, no puede usar `x:Shared` para los elementos de una <xref:System.Windows.ResourceDictionary> que se encuentre dentro de un <xref:System.Windows.Style> que ya sea un elemento de <xref:System.Windows.ResourceDictionary>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Elementos base](../wpf/advanced/base-elements.md)
