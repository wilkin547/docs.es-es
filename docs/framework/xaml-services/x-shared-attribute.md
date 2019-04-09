---
title: Atributo x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: da35f209b632bdf9e4ab2298239a505df69d6048
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125748"
---
# <a name="xshared-attribute"></a>Atributo x:Shared
Cuando se establece en `false`, modifica el comportamiento de recuperación de los recursos WPF para que las solicitudes para el recurso con atributos creación una nueva instancia para cada solicitud en lugar de compartir la misma instancia para todas las solicitudes.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Comentarios  
 `x:Shared` se asigna al espacio de nombres de XAML de lenguaje XAML y se reconoce como un elemento del lenguaje XAML válido por servicios XAML de .NET Framework y sus lectores XAML. Sin embargo, las capacidades comentadas de `x:Shared` solo son relevantes para las aplicaciones de WPF y para el analizador de WPF XAML. En WPF, `x:Shared` sólo es útil como un atributo cuando se aplica a un objeto que existe dentro de un WPF <xref:System.Windows.ResourceDictionary>. Otros usos no producen excepciones de análisis u otros errores, pero no tienen ningún efecto.  
  
 El significado de `x:Shared` no se especifica en la especificación del lenguaje XAML. Otras implementaciones de XAML, como los que se basan en los servicios XAML de .NET Framework, no necesariamente proporcionan compatibilidad con uso compartido de recursos. Estas implementaciones de XAML podrían proporcionar un comportamiento similar en el marco de apoyo que también usa `x:Shared` valores.  
  
 En WPF, el valor predeterminado `x:Shared` condición de recursos es `true`. Esta condición significa que cualquier solicitud de recurso devuelve siempre la misma instancia.  
  
 Modificar un objeto que se devuelve a través de un recurso de API, como <xref:System.Windows.FrameworkElement.FindResource%2A>, o modificar un objeto directamente dentro de un <xref:System.Windows.ResourceDictionary>, cambia el recurso original. Si las referencias a ese recurso eran recursos dinámicos, los consumidores de ese recurso obtención el recurso modificado.  
  
 Si las referencias al recurso eran recursos estáticos, los cambios en el recurso después [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tiempo de procesamiento son irrelevantes. Para obtener más información sobre estático o referencias de recursos dinámicos, consulte [recursos XAML](../wpf/advanced/xaml-resources.md).  
  
 Especificación explícita de `x:Shared="true"` es muy raro que ocurra, dado que ya es el valor predeterminado. No hay ningún código directo equivalente para `x:Shared` modelo de objetos en WPF; solo puede especificarse en el uso de XAML y deben procesarse mediante el comportamiento WPF predeterminado o en una secuencia de nodo XAML intermedia en la ruta de acceso de carga si se procesan mediante Se XAML de .NET Framework servicios y sus lectores XAML.  
  
 Un escenario para `x:Shared="false"` es si se define un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> derivados de la clase como un recurso y, a continuación, introduce el recurso del elemento en un modelo de contenido. `x:Shared="false"` permite que un recurso de elemento se introdujeron varias veces en la misma colección (como un <xref:System.Windows.Controls.UIElementCollection>). Sin `x:Shared="false"` esto no es válido porque la colección exige la unicidad de su contenido. Sin embargo, la `x:Shared="false"` comportamiento crea otra instancia idéntica de los recursos en lugar de devolver la misma instancia.  
  
 Otro escenario para `x:Shared="false"` cuando se usa un <xref:System.Windows.Freezable> recursos para los valores de animación pero desea modificar el recurso en cada animación.  
  
 El control de cadenas de `false` no distingue mayúsculas de minúsculas.  
  
 En WPF, `x:Shared` solo es válida en las siguientes condiciones:  
  
-   El <xref:System.Windows.ResourceDictionary> que contiene los elementos con `x:Shared` deben compilarse. El <xref:System.Windows.ResourceDictionary> no puede estar dentro de XAML flexible o utilizar para temas.  
  
-   El <xref:System.Windows.ResourceDictionary> que contiene los elementos no debe estar anidado dentro de otra <xref:System.Windows.ResourceDictionary>. Por ejemplo, no se puede usar `x:Shared` para los elementos de un <xref:System.Windows.ResourceDictionary> que está dentro de un <xref:System.Windows.Style> ya que está un <xref:System.Windows.ResourceDictionary> elemento.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.ResourceDictionary>
- [Recursos XAML](../wpf/advanced/xaml-resources.md)
- [Elementos base](../wpf/advanced/base-elements.md)
