---
title: x:Uid (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: b5b480016d2183268422dea861510c6a169ac27b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432621"
---
# <a name="xuid-directive"></a>x:Uid (Directiva)

Proporciona un identificador único para los elementos de marcado. En muchos escenarios, los procesos y las herramientas de localización XAML usan este identificador único.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object x:Uid="identifier"... />
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|`identifier`|Cadena creada manualmente o generada automáticamente que debe ser única en un `x:Uid` archivo cuando es interpretada por un consumidor.|

## <a name="remarks"></a>Observaciones

En [MS-XAML], `x:Uid` se define como una directiva. Para obtener más información, vea [ \[MS-XAML\] Sección 5.3.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid`es discreto `x:Name` desde ambos debido al escenario de localización XAML indicado y para que los identificadores que se usan para la localización no tengan dependencias en las implicaciones del modelo de programación de `x:Name`. Además, `x:Name` se rige por el ámbito de nombres XAML; sin `x:Uid` embargo, no se rige por ningún concepto definido por el lenguaje XAML de aplicación de la unicidad. No se espera que los procesadores XAML en un sentido amplio (procesadores que no forman parte del proceso de localización) apliquen la unicidad de `x:Uid` los valores. Esa responsabilidad reparte conceptualmente sobre el creador de los valores. La expectativa de `x:Uid` unicidad de valores dentro de un único origen XAML es razonable para los consumidores de los valores, como los procesos o herramientas de globalización dedicados. El modelo de unicidad típico es que `x:Uid` los valores son únicos dentro de un archivo codificado en XML que representa XAML.

Las herramientas que tienen un conocimiento significativo `x:Uid` de un esquema XAML determinado pueden optar por aplicar solo para cadenas localizables verdaderas, en lugar de para todos los casos donde se encuentra un valor de cadena de texto en el marcado.

Los marcos de trabajo pueden especificar una propiedad `x:Uid` determinada en su <xref:System.Windows.Markup.UidPropertyAttribute> modelo de objetos para que sea un alias aplicando el atributo al tipo de definición. Si un marco de trabajo especifica una propiedad `x:Uid` determinada, no es válido especificar ambos y el miembro con alias en el mismo objeto. Si `x:Uid` se especifican ambos y el miembro con alias, la <xref:System.Xaml.XamlDuplicateMemberException> API de servicios XAML de .NET normalmente se produce para este caso.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Para obtener más información `x:Uid` sobre el rol del proceso de localización de WPF y en el formulario BAML de XAML, vea [Globalización para WPF](../../framework/wpf/advanced/globalization-for-wpf.md) o<xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalización de WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
