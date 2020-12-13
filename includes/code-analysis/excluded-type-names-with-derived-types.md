---
ms.openlocfilehash: 150882f3e4c9ff7abe811e09da94b8141de75778
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366836"
---
### <a name="exclude-specific-types-and-their-derived-types"></a>Excluir tipos específicos y sus tipos derivados

Puede excluir tipos específicos y sus tipos derivados del análisis. Por ejemplo, para especificar que la regla no se debe ejecutar en ningún método de los tipos denominados `MyType` y sus tipos derivados, agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:

```ini
dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType
```

Formatos de nombre de símbolo permitidos en el valor de opción (separados por `|` ):

- Solo nombre de tipo (incluye todos los tipos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor).
- Nombres completos en el [formato de identificador de documentación](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings)del símbolo, con un `T:` prefijo opcional.

Ejemplos:

| Valor de la opción | Resumen |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType` | Coincide con todos los tipos denominados `MyType` y todos sus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = MyType1|MyType2` | Coincide con todos los tipos denominados `MyType1` o `MyType2` y todos sus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS.MyType` | Coincide con un tipo específico `MyType` con el nombre completo dado y todos sus tipos derivados. |
|`dotnet_code_quality.CAXXXX.excluded_type_names_with_derived_types = M:NS1.MyType1|M:NS2.MyType2` | Coincide con tipos específicos `MyType1` y `MyType2` con los nombres completos respectivos, y todos sus tipos derivados. |
