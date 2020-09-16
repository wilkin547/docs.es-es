---
title: x:Uid (Directiva)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], localizable content attribute
- XAML [XAML Services], x:Uid attribute
- x:Uid attribute [XAML Services]
- Uid attribute [XAML Services]
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
ms.openlocfilehash: 3de02702e6fd2be63bc2d099dad11f896b281ad1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543503"
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
|`identifier`|Cadena creada o generada automáticamente que debe ser única en un archivo cuando lo interpreta un `x:Uid` consumidor.|

## <a name="remarks"></a>Comentarios

En [MS-XAML], `x:Uid` se define como una directiva. Para obtener más información, vea [ \[ la \] sección MS-XAML 5.3.6](/previous-versions/msp-n-p/ff650760(v=pandp.10)).

`x:Uid` es discreto desde `x:Name` ambos debido al escenario de localización XAML indicado y para que los identificadores que se usan para la localización no tengan dependencias en las implicaciones del modelo de programación de `x:Name` . Además, `x:Name` se rige por el ámbito de nombres XAML; sin embargo, `x:Uid` no se rige por ningún concepto definido por el lenguaje XAML de cumplimiento de unicidad. No se espera que los procesadores XAML en un sentido amplio (los procesadores que no forman parte del proceso de localización) apliquen la unicidad de `x:Uid` los valores. Esa responsabilidad es conceptualmente en el creador de los valores. La expectativa de unicidad de `x:Uid` los valores dentro de un solo origen XAML es razonable para los consumidores de los valores, como las herramientas o los procesos de globalización dedicados. El modelo de unicidad típico es que `x:Uid` los valores son únicos en un archivo codificado en XML que representa XAML.

Las herramientas que tienen un conocimiento significativo de un esquema XAML determinado pueden optar por aplicarse `x:Uid` solo a las cadenas localizables verdaderas, en lugar de a todos los casos en los que se encuentra un valor de cadena de texto en el marcado.

Los marcos de trabajo pueden especificar una propiedad determinada en su modelo de objetos para que sea un alias de `x:Uid` aplicando el atributo <xref:System.Windows.Markup.UidPropertyAttribute> al tipo de definición. Si un marco de trabajo especifica una propiedad determinada, no es válido especificar tanto `x:Uid` como el miembro con alias en el mismo objeto. Si `x:Uid` se especifican y el miembro con alias, la API de servicios XAML de .net normalmente inicia <xref:System.Xaml.XamlDuplicateMemberException> en este caso.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

Para obtener más información sobre el rol de `x:Uid` en el proceso de localización de WPF y en el formulario BAML de XAML, vea [globalización de WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf) o <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>
- <xref:Microsoft.Build.Tasks.Windows.UidManager>
- [Globalización de WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
