---
ms.openlocfilehash: 83644b9205d650da68c910095dd1d22a14940c44
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "97366826"
---
### <a name="exclude-specific-symbols"></a>Excluir símbolos específicos

Puede excluir símbolos específicos, como tipos y métodos, del análisis. Por ejemplo, para especificar que la regla no se debe ejecutar en ningún código dentro de los tipos denominados `MyType` , agregue el siguiente par clave-valor a un archivo *. editorconfig* en el proyecto:

```ini
dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType
```

Formatos de nombre de símbolo permitidos en el valor de opción (separados por `|` ):

- Solo nombre de símbolo (incluye todos los símbolos con el nombre, sin tener en cuenta el tipo o espacio de nombres contenedor).
- Nombres completos en el [formato de ID](../../docs/csharp/programming-guide/xmldoc/processing-the-xml-file.md#id-strings). de documentación del símbolo. Cada nombre de símbolo requiere un prefijo de tipo símbolo, como `M:` para los métodos, `T:` para los tipos y `N:` para los espacios de nombres.
- `.ctor` para constructores y `.cctor` para constructores estáticos.

Ejemplos:

| Valor de la opción | Resumen |
| --- | --- |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType` | Coincide con todos los símbolos denominados `MyType` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = MyType1|MyType2` | Coincide con todos los símbolos denominados `MyType1` o `MyType2` . |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS.MyType.MyMethod(ParamType)` | Coincide `MyMethod` con un método específico con la firma completa especificada. |
|`dotnet_code_quality.CAXXXX.excluded_symbol_names = M:NS1.MyType1.MyMethod1(ParamType)|M:NS2.MyType2.MyMethod2(ParamType)` | Coincide con métodos específicos `MyMethod1` y `MyMethod2` con las firmas completas correspondientes. |
