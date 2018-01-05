---
title: Atributo x:Shared
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c9cc5e2bff9cc2591c7a12630da5422dbf73713a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xshared-attribute"></a>Atributo x:Shared
Cuando se establece en `false`, modifica el comportamiento de recuperación de los recursos WPF para que las solicitudes para el recurso con atributos crear una nueva instancia para cada solicitud en lugar de compartir la misma instancia para todas las solicitudes.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a>Comentarios  
 `x:Shared`se asigna al espacio de nombres de XAML de lenguaje XAML y se reconoce como un elemento de lenguaje XAML válido por servicios XAML de .NET Framework y sus lectores XAML. Sin embargo, las capacidades comentadas de `x:Shared` solo son relevantes para las aplicaciones WPF y para el analizador de XAML de WPF. En WPF, `x:Shared` sólo es útil como un atributo cuando se aplica a un objeto que se encuentra un WPF <xref:System.Windows.ResourceDictionary>. Otros usos no producen excepciones de análisis u otros errores, pero no tienen ningún efecto.  
  
 El significado de `x:Shared` no se especifica en la especificación del lenguaje XAML. Otras implementaciones de XAML, como los que se basan en los servicios XAML de .NET Framework, no proporcionan necesariamente la compatibilidad de uso compartido de recursos. Estas implementaciones XAML pudieron proporcionar un comportamiento similar en el marco de apoyo que también usa `x:Shared` valores.  
  
 En WPF, el valor predeterminado `x:Shared` condición de recursos es `true`. Esta condición significa que cualquier solicitud de recurso determinado siempre devuelve la misma instancia.  
  
 Modificar un objeto que se devuelve a través de un recurso de API, como <xref:System.Windows.FrameworkElement.FindResource%2A>, o modificar directamente un objeto dentro de un <xref:System.Windows.ResourceDictionary>, cambia el recurso original. Si las referencias a ese recurso eran dinámica de los recursos, los consumidores de ese recurso obtienen el recurso modificado.  
  
 Si las referencias al recurso eran recurso estático, cambios en el recurso después [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] tiempo de procesamiento no son relevantes. Para obtener más información acerca de estático frente a las referencias de recursos dinámicos, consulte [recursos XAML](../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
 Especificar explícitamente `x:Shared="true"` es muy poco habitual, dado que ya es el predeterminado. No hay ningún código directo equivalente para `x:Shared` en WPF el modelo de objetos; solo se puede especificar un uso de XAML y debe procesarse por el comportamiento WPF predeterminado o en un flujo de nodo XAML intermedio en la ruta de acceso de carga si se procesa mediante SAR de XAML de .NET Framework servicios y sus lectores XAML.  
  
 Un escenario para `x:Shared="false"` es si se define un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> deriva la clase como un recurso y, a continuación, introduce el recurso de elemento en un modelo de contenido. `x:Shared="false"`permite que un recurso de elemento que se introducen varias veces en la misma colección (como un <xref:System.Windows.Controls.UIElementCollection>). Sin `x:Shared="false"` esto no es válido porque la colección exige la unicidad de su contenido. Sin embargo, la `x:Shared="false"` comportamiento crea otra instancia idéntica del recurso en lugar de devolver la misma instancia.  
  
 Otro escenario para `x:Shared="false"` es si se usa un <xref:System.Windows.Freezable> recursos para los valores de animación pero desea modificar el recurso en cada animación.  
  
 El control de cadenas de `false` no distingue mayúsculas de minúsculas.  
  
 En WPF, `x:Shared` solo es válida en las siguientes condiciones:  
  
-   El <xref:System.Windows.ResourceDictionary> que contiene los elementos con `x:Shared` debe compilarse. El <xref:System.Windows.ResourceDictionary> no puede estar dentro de XAML dinámico o utilizar para temas.  
  
-   El <xref:System.Windows.ResourceDictionary> que contiene los elementos no debe estar anidado dentro de otra <xref:System.Windows.ResourceDictionary>. Por ejemplo, no se puede usar `x:Shared` para los elementos de un <xref:System.Windows.ResourceDictionary> que está dentro de un <xref:System.Windows.Style> ya que está un <xref:System.Windows.ResourceDictionary> elemento.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.ResourceDictionary>  
 [Recursos XAML](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Elementos base](../../../docs/framework/wpf/advanced/base-elements.md)
