---
title: x:Uid (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 6e946c63227a06b2032ce27e61899c1b8f05ec9f
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2019
ms.locfileid: "58042970"
---
# <a name="xuid-directive"></a>x:Uid (Directiva)
Proporciona un identificador único para los elementos de marcado. En muchos escenarios, se usa este identificador único mediante herramientas y procesos de localización de XAML.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`identifier`|Creada manualmente o cadena generada automáticamente que debe ser único en un archivo cuando lo interpreta un `x:Uid` consumidor.|  
  
## <a name="remarks"></a>Comentarios  
 En [MS-XAML] `x:Uid` se define como una directiva. Para obtener más información, consulte [ \[MS-XAML\] sección 5.3.6](https://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` es discreto desde `x:Name` ambos debido a la situación de localización de XAML indicada de forma que los identificadores que se usan para la localización no tienen ninguna dependencia en las implicaciones de modelo de programación de `x:Name`. Además, `x:Name` se rige por el ámbito de nombres XAML; sin embargo, `x:Uid` no se rige por ningún concepto de lenguaje definido de XAML de cumplimiento de unicidad. Procesadores XAML en un sentido amplio (procesadores que no forman parte del proceso de localización) no se esperan para exigir la exclusividad de `x:Uid` valores. Esa responsabilidad es conceptualmente en el autor de los valores. La expectativa de unicidad de `x:Uid` valores dentro de un único origen XAML es razonable para los consumidores de los valores, como los procesos de globalización dedicados o de herramientas. El modelo de singularidad típico es que `x:Uid` valores sean únicos dentro de un archivo con codificación XML que representa XAML.  
  
 Herramientas que tienen conocimientos importantes de un esquema XAML concreto pueden optar por aplicar `x:Uid` solo para "true" cadenas localizables, en lugar de para todos los casos donde se encuentra un valor de cadena de texto en el marcado.  
  
 Marcos de trabajo pueden especificar una propiedad determinada en su modelo de objetos sea un alias para `x:Uid` aplicando el atributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo de definición. Si un marco de trabajo especifica una propiedad determinada, no es válido especificar `x:Uid` y el miembro con alias en el mismo objeto. Si ambos `x:Uid` y se especifican el miembro con alias, la API de servicios XAML de .NET Framework se produce normalmente <xref:System.Xaml.XamlDuplicateMemberException> para este caso.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Para obtener más información acerca de la función `x:Uid` en el proceso de localización de WPF como en el formulario BAML de XAML, vea [globalización de WPF](../wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalización de WPF](../wpf/advanced/globalization-for-wpf.md)
