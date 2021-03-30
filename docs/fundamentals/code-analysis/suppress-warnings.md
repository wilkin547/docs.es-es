---
title: Supresión de advertencias de análisis de código
description: Obtenga más información sobre las distintas formas de suprimir infracciones de análisis del código de .NET.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: a8fdfbddd2393f9c6c8cd882a63a9ecc6cb1dc95
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105637044"
---
# <a name="how-to-suppress-code-analysis-warnings"></a>Procedimiento para suprimir advertencias de análisis de código

En este artículo se tratan las distintas formas de suprimir advertencias de análisis del código al compilar una aplicación de .NET.

> [!TIP]
> Si utiliza Visual Studio como entorno de desarrollo, el menú de *bombilla* proporciona opciones que generan el código para suprimir las advertencias. Para obtener más información, consulte [Supresión de infracciones](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).

## <a name="disable-the-rule"></a>Deshabilitación de la regla

Al deshabilitar la regla de análisis de código que causa la advertencia, deshabilitará la regla para todo el archivo o proyecto (según el ámbito del [archivo de configuración](configuration-files.md) que use). Para deshabilitar la regla, establezca su gravedad en `none` en el archivo de configuración.

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

Para obtener más información sobre los niveles de gravedad de las reglas, consulte [Nivel de gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level).

## <a name="use-a-preprocessor-directive"></a>Uso de una directiva de preprocesador

Use una directiva [Advertencia #pragma (C#)](../../csharp/language-reference/preprocessor-directives.md#pragma-warning) o [Deshabilitar (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) para suprimir la advertencia solo para una línea de código específica.

```csharp
    try { ... }
    catch (Exception e)
    {
#pragma warning disable CA2200 // Rethrow to preserve stack details
        throw e;
#pragma warning restore CA2200 // Rethrow to preserve stack details
    }
```

```vb
    Try
        ...
    Catch e As Exception
#Disable Warning CA2200 ' Rethrow to preserve stack details
        Throw e
#Enable Warning CA2200 ' Rethrow to preserve stack details
    End Try
```

## <a name="use-the-suppressmessageattribute"></a>Uso de SuppressMessageAttribute

Puede usar <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> para suprimir una advertencia en el archivo de código fuente o en un archivo de supresiones globales para el proyecto (*GlobalSuppressions.cs* o *GlobalSuppressions.vb*). Este atributo proporciona una manera de suprimir una advertencia solo en determinadas partes del proyecto o archivo.

Los dos parámetros posicionales requeridos para el atributo <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> son la *categoría* de la regla y el *identificador de la regla*. El siguiente fragmento de código pasa `"Usage"` y `"CA2200:Rethrow to preserve stack details"` para estos parámetros.

```csharp
[System.Diagnostics.CodeAnalysis.SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.")]
private static void IngorableCharacters()
{
    try
    {
        ...
    }
    catch (Exception e)
    {
        throw e;
    }
}
```

Si agrega el atributo al archivo de supresiones globales, el [ámbito](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) de la supresión quedará limitado al nivel deseado, por ejemplo, `"member"`. Especifique la API en la que se debe suprimir la advertencia mediante la propiedad <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target>.

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

En el caso del código generado por el compilador que no se asigna explícitamente al código fuente que el usuario ha proporcionado, para suprimir las advertencias debe colocar el atributo de supresión en un archivo de supresiones globales. Por ejemplo, el siguiente código suprime una infracción en un constructor emitido por el compilador:

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a>Vea también

- [Supresión de infracciones (Visual Studio)](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
