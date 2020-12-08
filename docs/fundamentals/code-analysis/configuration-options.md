---
title: Configurar reglas de análisis de código
description: Obtenga información sobre cómo configurar reglas de análisis de código en un archivo de configuración de analizador.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: 4f7b392a2b066023fec75c5295bd94651654d645
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851795"
---
# <a name="configuration-options-for-code-analysis"></a>Opciones de configuración para el análisis de código

Las reglas de análisis de código tienen varias opciones de configuración. Estas opciones se especifican como pares de clave y valor en un [archivo de configuración de analizador](configuration-files.md) mediante la sintaxis `<option key> = <option value>` .

La opción más común que va a configurar es la [gravedad de la regla](#severity-level). Puede configurar el nivel de gravedad para todas las reglas del analizador, incluidas las reglas de [calidad del código](quality-rules/index.md) y [las reglas de estilo de código](style-rules/index.md). Por ejemplo, para habilitar una regla como advertencia, puede Agregar el siguiente par clave-valor a un EditorConfig archivo.

`dotnet_diagnostic.<rule ID>.severity = warning`

También puede configurar opciones adicionales para personalizar el comportamiento de la regla:

- Las reglas de calidad de código tienen [opciones adicionales](code-quality-rule-options.md) para configurar el comportamiento, como los nombres de método a los que se debe aplicar una regla.
- Las reglas de estilo de código tienen [Opciones de estilo de código personalizado](code-style-rule-options.md).
- Las reglas del analizador de terceros pueden definir sus propias opciones de configuración, con nombres de clave personalizados y formatos de valor.

La sintaxis para configurar la gravedad de una regla específica en un [archivo de configuración de analizador](configuration-files.md) es la siguiente:

```ini
dotnet_diagnostic.<rule ID>.severity = <severity>
```

## <a name="general-options"></a>Opciones generales

Estas opciones se aplican al análisis de código en conjunto. No se pueden aplicar solo a una única regla o conjunto de reglas.

### <a name="exclude-generated-code"></a>Excluir código generado

Puede configurar archivos y carpetas adicionales para que se traten como código generado agregando una `generated_code = true | false` entrada al [archivo de configuración](configuration-files.md). Las advertencias del analizador de código de .NET no son útiles en los archivos de código generados, como los archivos generados por el diseñador, que los usuarios no pueden editar para corregir las infracciones. En la mayoría de los casos, los analizadores de código omiten los archivos de código generado y no informan de las infracciones de estos archivos.

De forma predeterminada, los archivos con determinadas extensiones de archivo o encabezados de archivo generados automáticamente se tratan como archivos de código generado. Por ejemplo, un nombre de archivo que termina con `.designer.cs` o `.generated.cs` se considera código generado. Esta opción de configuración permite especificar patrones de nomenclatura adicionales.

Por ejemplo, para tratar todos los archivos cuyo nombre termina con `.MyGenerated.cs` como código generado, agregue la entrada siguiente:

```ini
[*.MyGenerated.cs]
generated_code = true
```

## <a name="rule-specific-options"></a>Opciones específicas de la regla

Las opciones específicas de la regla se pueden aplicar a una sola regla, a un conjunto de reglas o a todas las reglas. Las opciones específicas de la regla incluyen:

- [Nivel de gravedad de la regla](#severity-level)
- [Opciones específicas de las reglas *de calidad de código*](code-quality-rule-options.md)

### <a name="severity-level"></a>Nivel de gravedad

En la tabla siguiente se muestran los diferentes niveles de gravedad de la regla que se pueden configurar para todas las reglas del analizador, incluidas las reglas de [calidad de código](quality-rules/index.md) y [estilo de código](style-rules/index.md) .

| severity | Comportamiento en tiempo de compilación |
|-|-|
| `error` | Las infracciones aparecen como *errores* de compilación y producen errores en las compilaciones.|
| `warning` | Las infracciones aparecen como *advertencias* de compilación, pero no hacen que se produzca un error en las compilaciones (a menos que tenga una opción establecida para tratar advertencias como errores). |
| `suggestion` | Las infracciones aparecen como *mensajes* de compilación y como sugerencias en el IDE de Visual Studio. |
| `silent` | Las infracciones no son visibles para el usuario. |
| `none` | La regla se suprime por completo. |
| `default` | Se usa la gravedad predeterminada de la regla. |

> [!TIP]
> Para obtener información sobre cómo se exponen las gravedades de las reglas en Visual Studio, vea [niveles de gravedad](/visualstudio/ide/editorconfig-language-conventions#severity-levels).

#### <a name="scope"></a>Ámbito

Para establecer la gravedad de la regla para una sola regla, use la sintaxis siguiente.

```ini
dotnet_diagnostic.<rule ID>.severity = <severity value>
```

Para establecer la gravedad de la regla predeterminada para una categoría de reglas del analizador, use la sintaxis siguiente.

```ini
dotnet_analyzer_diagnostic.category-<rule category>.severity = <severity value>
```

Para establecer la gravedad de la regla predeterminada para todas las reglas del analizador, use la siguiente sintaxis.

```ini
dotnet_analyzer_diagnostic.severity = <severity value>
```

#### <a name="precedence"></a>Prioridad

Si tiene varias entradas de configuración de gravedad que se pueden aplicar al mismo identificador de regla, la prioridad se elige en el orden siguiente:

- Una entrada para una regla individual por identificador tiene prioridad sobre una entrada para una categoría.
- Una entrada para una categoría tiene prioridad sobre una entrada para todas las reglas del analizador.

Considere el ejemplo siguiente, donde [CA1822](/visualstudio/code-quality/ca1822) tiene la categoría "performance":

```ini
[*.cs]
dotnet_diagnostic.CA1822.severity = error
dotnet_analyzer_diagnostic.category-performance.severity = warning
dotnet_analyzer_diagnostic.severity = suggestion
```

En el ejemplo anterior, las tres entradas de gravedad se aplican a CA1822. Sin embargo, con las reglas de precedencia especificadas, la primera entrada basada en el identificador de regla gana sobre las siguientes entradas. En este ejemplo, CA1822 tendrá una gravedad efectiva de `error` . Todas las demás reglas de la categoría "rendimiento" tendrán una gravedad de `warning` .

Para obtener información sobre cómo se decide la precedencia entre archivos, vea la [sección de precedencia del artículo archivos de configuración](configuration-files.md#precedence).
