---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617278"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a>El análisis de System.Uri cumple con las disposiciones de RFC 3987

#### <a name="details"></a>Detalles

El análisis de URI se ha modificado de varias formas en .NET Framework 4.5. Pero tenga en cuenta que estos cambios solo afectan al código que tenga como destino .NET Framework 4.5. Si un binario tiene como destino .NET Framework 4.0, se observará el comportamiento anterior. Entre los cambios efectuados en el análisis de URI en .NET Framework 4.5 se incluyen los siguientes:

- Los análisis de identificadores URI efectuarán comprobaciones de normalización y caracteres conforme a las normas más recientes sobre IRI indicadas en RFC 3987.
- La forma de normalización C de Unicode solo se ejecutará en la sección de host del identificador URI.
- Mailto no válido: Los identificadores URI ahora generarán una excepción.
- Ahora se conservan los puntos finales al final de un segmento de trazado.
- Los identificadores URI de `file://` no aplican secuencias de escape al carácter `?`.
- Los caracteres de control Unicode `U+0080` a `U+009F` no son compatibles.
- Las secuencias de escape de los caracteres de coma `,` y `%2c` no se eliminan automáticamente.

#### <a name="suggestion"></a>Sugerencia

Si es necesario usar la semántica de análisis de URI anterior de .NET Framework 4.0 (lo que no es habitual), se puede usar si se selecciona .NET Framework 4.0 como destino. Esto se puede hacer mediante un atributo <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> en el ensamblado, o bien a través de la interfaz de usuario del sistema del proyecto de Visual Studio, en la página "Propiedades del proyecto".

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.5         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
