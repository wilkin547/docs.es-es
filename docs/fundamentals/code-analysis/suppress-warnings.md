---
title: Suprimir advertencias de análisis de código
description: Obtenga información sobre las distintas formas en las que puede suprimir las infracciones de análisis de código .NET.
ms.date: 01/28/2021
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- code analysis, suppress warnings
- suppress code analysis warnings
ms.openlocfilehash: b08e93089975a59fabfeb0daaf6a2a6454b2c7e8
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "99217268"
---
# <a name="how-to-suppress-code-analysis-warnings"></a>Cómo suprimir advertencias de análisis de código

En este artículo se tratan las distintas formas en las que puede suprimir las advertencias del análisis de código al compilar la aplicación .NET.

> [!TIP]
> Si utiliza Visual Studio como entorno de desarrollo, el menú de *bombilla* proporciona opciones que generan el código para suprimir las advertencias. Para obtener más información, vea [suprimir infracciones](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations).

## <a name="disable-the-rule"></a>Deshabilitar la regla

Al deshabilitar la regla de análisis de código que está causando la advertencia, deshabilitará la regla para todo el archivo o proyecto (según el ámbito del [archivo de configuración](configuration-files.md) que use). Para deshabilitar la regla, establezca su gravedad `none` en en el archivo de configuración.

```ini
[*.{cs,vb}]
dotnet_diagnostic.<rule-ID>.severity = none
```

Para obtener más información sobre los niveles de gravedad de las reglas, consulte [configurar la gravedad](~/docs/fundamentals/code-analysis/configuration-options.md#severity-level)de la regla.

## <a name="use-a-preprocessor-directive"></a>Usar una directiva de preprocesador

Utilice una directiva [#pragma warning (C#)](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) o [disable (Visual Basic)](../../visual-basic/language-reference/directives/disable-enable.md) para suprimir la advertencia solo para una línea de código específica.

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

## <a name="use-the-suppressmessageattribute"></a>Usar el SuppressMessageAttribute

Puede usar un <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> para suprimir una advertencia en el archivo de código fuente o en un archivo de supresiones globales para el proyecto (*GlobalSuppressions.CS* o *GlobalSuppressions. VB*). Este atributo proporciona una manera de suprimir una advertencia solo en determinadas partes del proyecto o archivo.

Los dos parámetros posicionales obligatorios para el <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> atributo son la *categoría* de la regla y el *identificador* de la regla. El siguiente fragmento de código pasa `"Usage"` y `"CA2200:Rethrow to preserve stack details"` para estos parámetros.

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

Si agrega el atributo al archivo de supresiones globales, el [ámbito](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) de la supresión se limita al nivel deseado, por ejemplo `"member"` . Especifique la API en la que se debe suprimir la advertencia mediante la <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Target> propiedad.

```csharp
[assembly: SuppressMessage("Usage", "CA2200:Rethrow to preserve stack details", Justification = "Not production code.", Scope = "member", Target = "~M:MyApp.Program.IngorableCharacters")]
```

Para suprimir las advertencias del código generado por el compilador que no se asignan al origen de usuario proporcionado explícitamente, debe colocar el atributo de supresión en un archivo de supresiones global. Por ejemplo, el siguiente código suprime una infracción en un constructor emitido por compilador:

```csharp
[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="MyTools.Type..ctor()")]
```

## <a name="see-also"></a>Vea también

- [Suprimir infracciones (Visual Studio)](/visualstudio/code-quality/use-roslyn-analyzers?#suppress-violations)
