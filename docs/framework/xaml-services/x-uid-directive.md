---
title: x:Uid (Directiva)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9abd4a1851ce21a1858f51ff4ce42998c20639e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xuid-directive"></a>x:Uid (Directiva)
Proporciona un identificador único para los elementos de marcado. En muchos escenarios, este identificador único se usa por los procesos de localización de XAML y las herramientas.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`identifier`|Creada manualmente o cadena generada automáticamente que debe ser único en un archivo cuando lo interpreta un `x:Uid` consumidor.|  
  
## <a name="remarks"></a>Comentarios  
 En [MS-XAML] `x:Uid` se define como una directiva. Para obtener más información, consulte [ \[MS-XAML\] sección 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid`moderado de `x:Name` ambos debido a lo indicado escenario de localización de XAML de modo que los identificadores que se utilizan para la localización no tienen ninguna dependencia en las implicaciones del modelo de programación de `x:Name`. Además, `x:Name` se rige por el ámbito de nombres XAML; sin embargo, `x:Uid` no se rige por ningún concepto de idioma definido de XAML de cumplimiento de unicidad. Los procesadores XAML en un sentido amplio (procesadores que no forman parte del proceso de localización) no están pensados para exigir la exclusividad de `x:Uid` valores. Esa responsabilidad es conceptualmente en el autor de los valores. La expectativa de singularidad de `x:Uid` valores dentro de un único origen XAML es razonable para los consumidores de los valores, como los procesos de globalización dedicados o herramientas. El modelo de singularidad típico es que `x:Uid` los valores son únicos dentro de un archivo codificado en XML que representa XAML.  
  
 Herramientas que tienen un conocimiento significativo de un esquema XAML determinado pueden optar por aplicar `x:Uid` solo para true cadenas localizables, en lugar de en todos los casos donde se encuentra un valor de cadena de texto en el marcado.  
  
 Marcos de trabajo pueden especificar una propiedad determinada en su modelo de objetos como un alias para `x:Uid` aplicando el atributo <xref:System.Windows.Markup.UidPropertyAttribute> para el tipo de definición. Si un marco de trabajo especifica una propiedad determinada, no es válido especificar `x:Uid` y el miembro tiene un alias en el mismo objeto. Si ambos `x:Uid` y se especifican los miembros de un alias, la API de servicios XAML de .NET Framework se produce normalmente <xref:System.Xaml.XamlDuplicateMemberException> en este caso.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 Para obtener más información acerca de la función de `x:Uid` en el proceso de localización de WPF y en el formulario BAML de XAML, vea [globalización de WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) o<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
 <xref:Microsoft.Build.Tasks.Windows.UidManager>  
 [Globalización de WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
