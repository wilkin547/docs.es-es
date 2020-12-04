---
title: Opciones de configuración de reglas de calidad de código
description: Obtenga información sobre cómo especificar opciones de configuración adicionales para las reglas de calidad del código.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: af2984e73c554e8a1e1b32df9460933f86cc41be
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592571"
---
# <a name="code-quality-rule-configuration-options"></a>Opciones de configuración de reglas de calidad de código

Las reglas de *calidad del código* tienen opciones de configuración adicionales, además de [configurar su gravedad](configuration-options.md#severity-level). Por ejemplo, cada analizador de calidad de código puede configurarse para que solo se aplique a partes específicas de su código base. Estas opciones se especifican agregando pares de clave-valor al mismo [EditorConfig](https://editorconfig.org) archivo en el que se especifican los niveles de gravedad y las preferencias generales del editor.

## <a name="option-scopes"></a>Ámbitos de opción

Cada opción de refinamiento se puede configurar para todas las reglas, para una categoría de reglas (por ejemplo, seguridad o diseño) o para una regla específica.

### <a name="all-rules"></a>Todas las reglas

La sintaxis para configurar una opción para *todas* las reglas es la siguiente:

|Sintaxis|Ejemplo|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>Categoría de reglas

La sintaxis para configurar una opción para una *categoría* de reglas (como nombre, diseño o rendimiento) es la siguiente:

|Sintaxis|Ejemplo|
|-|-|
| dotnet_code_quality.RuleCategory.OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>Regla específica

La sintaxis para configurar una opción para una regla *específica* es la siguiente:

|Sintaxis|Ejemplo|
|-|-|
| dotnet_code_quality. . Nombredeopción = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="options"></a>Opciones

En esta sección se enumeran algunas de las opciones disponibles. Para ver la lista completa de las opciones disponibles, vea [configuración del analizador](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md).

### <a name="api_surface"></a>api_surface

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Qué parte de la superficie de API se va a analizar | `public`<br/>`internal` o `friend`<br/>`private`<br/>`all`<br/><br/>Separar varios valores con una coma (,) | `public` | [CA1000](quality-rules/ca1000.md) [CA1003](quality-rules/ca1003.md) [CA1008](quality-rules/ca1008.md) [CA1010](quality-rules/ca1010.md)<br/>[CA1012](quality-rules/ca1012.md) [CA1024](quality-rules/ca1024.md) [CA1027](quality-rules/ca1027.md) [CA1028](quality-rules/ca1028.md)<br/>[CA1030](quality-rules/ca1030.md) [CA1036](quality-rules/ca1036.md) [CA1040](quality-rules/ca1040.md) [CA1041](quality-rules/ca1041.md)<br/>[CA1043](quality-rules/ca1043.md) [CA1044](quality-rules/ca1044.md) [CA1051](quality-rules/ca1051.md) [CA1052](quality-rules/ca1052.md)<br/>[CA1054](quality-rules/ca1054.md) [CA1055](quality-rules/ca1055.md) [CA1056](quality-rules/ca1056.md) [CA1058](quality-rules/ca1058.md)<br/>[CA1063](quality-rules/ca1063.md) [CA1708](quality-rules/ca1708.md) [CA1710](quality-rules/ca1710.md) [CA1711](quality-rules/ca1711.md)<br/>[CA1714](quality-rules/ca1714.md) [CA1715](quality-rules/ca1715.md) [CA1716](quality-rules/ca1716.md) [CA1717](quality-rules/ca1717.md)<br/>[CA1720](quality-rules/ca1720.md) [CA1721](quality-rules/ca1721.md) [CA1725](quality-rules/ca1725.md) [CA1801](quality-rules/ca1801.md)<br/>[CA1802](quality-rules/ca1802.md) [CA1815](quality-rules/ca1815.md) [CA1819](quality-rules/ca1819.md) [CA2217](quality-rules/ca2217.md)<br/>[CA2225](quality-rules/ca2225.md) [CA2226](quality-rules/ca2226.md) [CA2231](quality-rules/ca2231.md) [CA2234](quality-rules/ca2234.md)<br/>|

### <a name="exclude_async_void_methods"></a>exclude_async_void_methods

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Si se omiten los métodos asincrónicos que no devuelven un valor | `true`<br/>`false` | `false` | [CA2007](quality-rules/ca2007.md) |

> [!NOTE]
> Esta opción se denominaba `skip_async_void_methods` en una versión anterior.

### <a name="exclude_single_letter_type_parameters"></a>exclude_single_letter_type_parameters

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Si se van a excluir de la regla [los parámetros de tipo](../../csharp/programming-guide/generics/generic-type-parameters.md) de un solo carácter, por ejemplo, `S` en `Collection<S>` | `true`<br/>`false` | `false` | [CA1715](quality-rules/ca1715.md) |

> [!NOTE]
> Esta opción se denominaba `allow_single_letter_type_parameters` en una versión anterior.

### <a name="output_kind"></a>output_kind

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Especifica que debe analizarse el código de un proyecto que genera este tipo de ensamblado. | Uno o más campos de la <xref:Microsoft.CodeAnalysis.OutputKind> enumeración<br/><br/>Separar varios valores con una coma (,) | Todos los tipos de salida | [CA2007](quality-rules/ca2007.md) |

### <a name="required_modifiers"></a>required_modifiers

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Especifica los modificadores necesarios para las API que se deben analizar. | Uno o más valores de la siguiente tabla de modificadores permitidos<br/><br/>Separar varios valores con una coma (,) | Depende de cada regla | [CA1802](quality-rules/ca1802.md) |

| Modificador permitido | Resumen |
| --- | --- |
| `none` | No hay ningún requisito modificador |
| `static` o `Shared` | Se debe declarar como `static` ( `Shared` en Visual Basic) |
| `const` | Se debe declarar como `const` |
| `readonly` | Se debe declarar como `readonly` |
| `abstract` | Se debe declarar como `abstract` |
| `virtual` | Se debe declarar como `virtual` |
| `override` | Se debe declarar como `override` |
| `sealed` | Se debe declarar como `sealed` |
| `extern` | Se debe declarar como `extern` |
| `async` | Se debe declarar como `async` |

### <a name="exclude_extension_method_this_parameter"></a>exclude_extension_method_this_parameter

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Indica si se omitirá el análisis del `this` parámetro de los métodos de extensión | `true`<br/>`false` | `false` | [CA1062](quality-rules/ca1062.md) |

### <a name="null_check_validation_methods"></a>null_check_validation_methods

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Los nombres de métodos de validación de comprobación nula que validan que los argumentos pasados al método no son NULL | Formatos de nombre de método permitidos (separados por `|` ):<br/> -Solo nombre del método (incluye todos los métodos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor)<br/> -Nombres completos en el [formato de identificador de documentación](https://github.com/dotnet/csharplang/blob/master/spec/documentation-comments.md#id-string-format)del símbolo, con un `M:` prefijo opcional | Ninguno | [CA1062](quality-rules/ca1062.md) |

### <a name="additional_string_formatting_methods"></a>additional_string_formatting_methods

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Nombres de métodos de formato de cadena adicionales | Formatos de nombre de método permitidos (separados por `|` ):<br/> -Solo nombre del método (incluye todos los métodos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor)<br/> -Nombres completos en el [formato de identificador de documentación](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)del símbolo, con un `M:` prefijo opcional | Ninguno | [CA2241](quality-rules/ca2241.md) |

### <a name="excluded_type_names_with_derived_types"></a>excluded_type_names_with_derived_types

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Nombres de tipos, de modo que el tipo y todos sus tipos derivados se excluyen para el análisis | Formatos de nombre de símbolos permitidos (separados por `|` ):<br/> -Solo nombre de tipo (incluye todos los tipos con el nombre, independientemente del tipo o espacio de nombres contenedor)<br/> -Nombres completos en el [formato de identificador de documentación](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format)del símbolo, con un `T:` prefijo opcional | Ninguno | [CA1303](quality-rules/ca1303.md) |

### <a name="excluded_symbol_names"></a>excluded_symbol_names

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Nombres de los símbolos que se excluyen para el análisis | Formatos de nombre de símbolos permitidos (separados por `|` ):<br/> -Solo nombre de símbolo (incluye todos los símbolos con el nombre, independientemente del tipo o espacio de nombres contenedor)<br/> -Nombres completos en el [formato de ID](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format). de documentación del símbolo. Cada nombre de símbolo requiere un prefijo de tipo de símbolo, como el `M:` Prefijo de los métodos, el prefijo `T:` para los tipos y el `N:` prefijo para los espacios de nombres.<br/> - `.ctor` para constructores y `.cctor` para constructores estáticos | Ninguno | [CA1062](quality-rules/ca1062.md) [CA1303](quality-rules/ca1303.md) [CA2000](quality-rules/ca2000.md) [CA2100](quality-rules/ca2100.md) [CA2301](quality-rules/ca2301.md) [CA2302](quality-rules/ca2302.md)<br/>[CA2311](quality-rules/ca2311.md) [CA2312](quality-rules/ca2312.md) [CA2321](quality-rules/ca2321.md) [CA2322](quality-rules/ca2322.md) [CA2327](quality-rules/ca2327.md) [CA2328](quality-rules/ca2328.md)<br/>[CA2329](quality-rules/ca2329.md) [CA2330](quality-rules/ca2330.md) [CA3001](quality-rules/ca3001.md) [CA3002](quality-rules/ca3002.md) [CA3003](quality-rules/ca3003.md) [CA3004](quality-rules/ca3004.md)<br/>[CA3005](quality-rules/ca3005.md) [CA3006](quality-rules/ca3006.md) [CA3007](quality-rules/ca3007.md) [CA3008](quality-rules/ca3008.md) [CA3009](quality-rules/ca3009.md) [CA3010](quality-rules/ca3010.md)<br/>[CA3011](quality-rules/ca3011.md) [CA3012](quality-rules/ca3012.md) [CA5361](quality-rules/ca5361.md) CA5376 CA5377 [CA5378](quality-rules/ca5378.md)<br/>[CA5380](quality-rules/ca5380.md) [CA5381](quality-rules/ca5381.md) CA5382 CA5383 CA5384 CA5387<br/>CA5388 [CA5389](quality-rules/ca5389.md) CA5390 |

### <a name="disallowed_symbol_names"></a>disallowed_symbol_names

| Descripción | Valores permitidos | Valor predeterminado | Reglas configurables |
| - | - | - | - |
| Nombres de los símbolos que no se permiten en el contexto del análisis | Formatos de nombre de símbolos permitidos (separados por `|` ):<br/> -Solo nombre de símbolo (incluye todos los símbolos con el nombre, independientemente del tipo o espacio de nombres contenedor)<br/> -Nombres completos en el [formato de ID](/dotnet/csharp/language-reference/language-specification/documentation-comments#id-string-format). de documentación del símbolo. Cada nombre de símbolo requiere un prefijo de tipo de símbolo, como el `M:` Prefijo de los métodos, el prefijo `T:` para los tipos y el `N:` prefijo para los espacios de nombres.<br/> - `.ctor` para constructores y `.cctor` para constructores estáticos | Ninguno | [CA1031](quality-rules/ca1031.md) |
