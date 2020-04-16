---
title: Atributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432651"
---
# <a name="xshared-attribute"></a>Atributo x:Shared

Cuando se `false`establece en , modifica el comportamiento de recuperación de recursos de WPFWPF para que las solicitudes del recurso con atributos creen una nueva instancia para cada solicitud en lugar de compartir la misma instancia para todas las solicitudes.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Observaciones

`x:Shared`se asigna al espacio de nombres XAML del lenguaje XAML y los servicios XAML de .NET y sus lectores XAML reconocen como un elemento de lenguaje XAML válido. Sin embargo, `x:Shared` las capacidades indicadas de solo son relevantes para las aplicaciones WPFWPF y para el analizador XAML de WPF. En WPFWPF, `x:Shared` solo es útil como atributo cuando se aplica <xref:System.Windows.ResourceDictionary>a un objeto que existe dentro de WPFWPF . Otros usos no producen excepciones de análisis u otros errores, pero no tienen ningún efecto.

El significado `x:Shared` de no se especifica en la especificación del lenguaje XAML. Otras implementaciones XAML, como las que se basan en servicios XAML de .NET, no proporcionan necesariamente compatibilidad con el uso compartido de recursos. Estas implementaciones XAML podrían proporcionar un comportamiento `x:Shared` similar en el marco de trabajo de soporte que también usa valores.

En WPFWPF, `x:Shared` la condición predeterminada para los recursos es `true`. Esta condición significa que cualquier solicitud de recurso determinada siempre devuelve la misma instancia.

Modificar un objeto que se devuelve a <xref:System.Windows.FrameworkElement.FindResource%2A>través de una <xref:System.Windows.ResourceDictionary>API de recursos, como , o modificar un objeto directamente dentro de un , cambia el recurso original. Si las referencias a ese recurso eran referencias de recursos dinámicos, los consumidores de ese recurso obtienen el recurso modificado.

Si las referencias al recurso eran referencias de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] recursos estáticos, los cambios en el recurso después del tiempo de procesamiento son irrelevantes. Para obtener más información acerca de las referencias de recursos estáticos frente a dinámicos, vea [Recursos XAML](../fundamentals/xaml-resources-define.md).

La especificación `x:Shared="true"` explícita rara vez se hace, porque eso ya es el valor predeterminado. No hay ningún equivalente `x:Shared` de código directo para en el WPFWPF modelo de objetos; solo se puede especificar en un uso XAML y debe procesarse mediante el comportamiento predeterminado de WPFWPF o en un flujo de nodo XAML intermedio en la ruta de acceso de carga si se procesa mediante los servicios XAML de .NET y sus lectores XAML.

Un escenario `x:Shared="false"` para es <xref:System.Windows.FrameworkElement> si <xref:System.Windows.FrameworkContentElement> define una clase derivada o como un recurso y, a continuación, introduce el recurso de elemento en un modelo de contenido. `x:Shared="false"`permite que un recurso de elemento se introduzca varias <xref:System.Windows.Controls.UIElementCollection>veces en la misma colección (por ejemplo, un ). Sin `x:Shared="false"` esto no es válido porque la colección aplica la unicidad de su contenido. Sin `x:Shared="false"` embargo, el comportamiento crea otra instancia idéntica del recurso en lugar de devolver la misma instancia.

Otro escenario `x:Shared="false"` para es <xref:System.Windows.Freezable> si usa un recurso para los valores de animación, pero desea modificar el recurso por animación.

El control `false` de cadenas de no distingue mayúsculas de minúsculas.

En WPFWPF, `x:Shared` solo es válido en las siguientes condiciones:

- El <xref:System.Windows.ResourceDictionary> que contiene `x:Shared` los elementos con debe compilarse. No <xref:System.Windows.ResourceDictionary> se puede estar dentro de XAML suelto o se usa para temas.

- El <xref:System.Windows.ResourceDictionary> que contiene los elementos <xref:System.Windows.ResourceDictionary>no debe anidarse dentro de otro . Por ejemplo, no `x:Shared` se puede <xref:System.Windows.ResourceDictionary> usar para <xref:System.Windows.Style> los elementos de un que ya está dentro de un elemento que ya está un <xref:System.Windows.ResourceDictionary> elemento.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](../fundamentals/xaml-resources-define.md)
- [Elementos base](../../framework/wpf/advanced/base-elements.md)
