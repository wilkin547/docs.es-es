---
title: x:Uid (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 32cfd9ab0cf6037c731b619e81a7504ac92d5fb9
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837186"
---
# <a name="xuid-directive"></a>x:Uid (Directiva)
Proporciona un identificador único para los elementos de marcado. En muchos escenarios, los procesos y las herramientas de localización de XAML usan este identificador único.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object x:Uid="identifier"... />  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`identifier`|Cadena creada o generada automáticamente que debe ser única en un archivo cuando lo interpreta un consumidor `x:Uid`.|  
  
## <a name="remarks"></a>Notas  
 En [MS-XAML], `x:Uid` se define como una directiva. Para obtener más información, vea [\[sección de\] MS-XAML 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
 `x:Uid` es discreto de `x:Name` debido al escenario de localización de XAML indicado y para que los identificadores que se usan para la localización no tengan dependencias en las implicaciones del modelo de programación de `x:Name`. Además, `x:Name` se rige por el ámbito de nombres XAML; sin embargo, `x:Uid` no se rige por ningún concepto definido por el lenguaje XAML de cumplimiento de unicidad. No se espera que los procesadores XAML en un sentido amplio (los procesadores que no forman parte del proceso de localización) apliquen la unicidad de los valores de `x:Uid`. Esa responsabilidad es conceptualmente en el creador de los valores. La expectativa de unicidad de los valores de `x:Uid` dentro de un solo origen XAML es razonable para los consumidores de los valores, como las herramientas o los procesos de globalización dedicados. El modelo de unicidad típico es que `x:Uid` valores son únicos en un archivo codificado en XML que representa XAML.  
  
 Las herramientas que tienen un conocimiento significativo de un esquema XAML determinado pueden optar por aplicar `x:Uid` solo para cadenas localizables verdaderas, en lugar de para todos los casos en los que se encuentra un valor de cadena de texto en el marcado.  
  
 Los marcos de trabajo pueden especificar que una propiedad determinada en su modelo de objetos sea un alias de `x:Uid` aplicando el atributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo de definición. Si un marco de trabajo especifica una propiedad determinada, no es válido especificar tanto `x:Uid` como el miembro con alias en el mismo objeto. Si se especifican `x:Uid` y el miembro con alias, la API de servicios XAML .NET Framework normalmente inicia <xref:System.Xaml.XamlDuplicateMemberException> para este caso.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 Para obtener más información sobre el rol de `x:Uid` en el proceso de localización de WPF y en el formulario BAML de XAML, vea [globalización de WPF](../wpf/advanced/globalization-for-wpf.md) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalización de WPF](../wpf/advanced/globalization-for-wpf.md)
