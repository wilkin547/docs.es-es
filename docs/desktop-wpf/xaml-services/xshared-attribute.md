---
title: Atributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557793"
---
# <a name="xshared-attribute"></a>Atributo x:Shared

Cuando se establece en `false` , modifica el comportamiento de recuperación de recursos de WPF para que las solicitudes del recurso con atributos creen una nueva instancia para cada solicitud en lugar de compartir la misma instancia para todas las solicitudes.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Comentarios

`x:Shared` se asigna al espacio de nombres XAML del lenguaje XAML y se reconoce como un elemento de lenguaje XAML válido por los servicios XAML de .NET y sus lectores XAML. Sin embargo, las capacidades indicadas de `x:Shared` solo son relevantes para las aplicaciones de WPF y para el analizador XAML de WPF. En WPF, `x:Shared` solo es útil como atributo cuando se aplica a un objeto que existe dentro de un WPF <xref:System.Windows.ResourceDictionary> . Otros usos no producen excepciones de análisis u otros errores, pero no tienen ningún efecto.

El significado de `x:Shared` no se especifica en la especificación del lenguaje XAML. Otras implementaciones de XAML, como las que se basan en los servicios XAML de .NET, no proporcionan necesariamente compatibilidad con el uso compartido de recursos. Estas implementaciones de XAML podrían proporcionar un comportamiento similar en el marco de trabajo compatible que también usa `x:Shared` valores.

En WPF, la `x:Shared` condición predeterminada de los recursos es `true` . Esta condición significa que cualquier solicitud de recurso determinada siempre devuelve la misma instancia.

La modificación de un objeto que se devuelve a través de una API de recursos, como <xref:System.Windows.FrameworkElement.FindResource%2A> , o la modificación de un objeto directamente dentro de un <xref:System.Windows.ResourceDictionary> , cambia el recurso original. Si las referencias a ese recurso eran referencias de recursos dinámicos, los consumidores de ese recurso obtienen el recurso modificado.

Si las referencias al recurso eran referencias de recursos estáticos, los cambios en el recurso después del [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tiempo de procesamiento son irrelevantes. Para obtener más información sobre las referencias de recursos estáticos y dinámicos, vea [recursos XAML](../fundamentals/xaml-resources-define.md).

Si se especifica explícitamente `x:Shared="true"` , se suele hacer porque ya es el valor predeterminado. No hay ningún equivalente de código directo para `x:Shared` en el modelo de objetos de WPF; solo se puede especificar en un uso de XAML y debe procesarse mediante el comportamiento predeterminado de WPF o en un flujo de nodo XAML intermedio en la ruta de acceso de carga, si se procesa mediante los servicios XAML de .net y sus lectores XAML.

Un escenario para `x:Shared="false"` es si define una <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> clase derivada de o como un recurso y, a continuación, introduce el recurso de elemento en un modelo de contenido. `x:Shared="false"` permite que un recurso de elemento se introduzca varias veces en la misma colección (por ejemplo, <xref:System.Windows.Controls.UIElementCollection> ). Sin `x:Shared="false"` esto no es válido porque la colección exige la unicidad de su contenido. Sin embargo, el `x:Shared="false"` comportamiento crea otra instancia idéntica del recurso en lugar de devolver la misma instancia.

Otro escenario para `x:Shared="false"` es si usa un <xref:System.Windows.Freezable> recurso para los valores de animación pero desea modificar el recurso por animación.

El control de cadenas de `false` no distingue entre mayúsculas y minúsculas.

En WPF, `x:Shared` solo es válido en las siguientes condiciones:

- <xref:System.Windows.ResourceDictionary>Que contiene los elementos con `x:Shared` se debe compilar. <xref:System.Windows.ResourceDictionary>No puede estar dentro de un código XAML dinámico ni usarse para los temas.

- El <xref:System.Windows.ResourceDictionary> que contiene los elementos no debe estar anidado dentro de otro <xref:System.Windows.ResourceDictionary> . Por ejemplo, no puede utilizar `x:Shared` para los elementos de <xref:System.Windows.ResourceDictionary> que se encuentran en un <xref:System.Windows.Style> que ya es un <xref:System.Windows.ResourceDictionary> elemento.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](../fundamentals/xaml-resources-define.md)
- [Elementos base](/dotnet/desktop/wpf/advanced/base-elements)
