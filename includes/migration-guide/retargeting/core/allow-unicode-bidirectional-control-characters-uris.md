---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614632"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a>Permitir caracteres de control bidireccional de Unicode en los URI

#### <a name="details"></a>Detalles

Unicode especifica varios caracteres de control especiales que se usan para especificar la orientación del texto. En versiones anteriores de .NET Framework, estos caracteres se quitaban incorrectamente de todos los URI, incluso si ya estaban presentes en su forma codificada por porcentaje. Para seguir [RFC 3987](https://tools.ietf.org/html/rfc3987) mejor, ahora se permiten estos caracteres en los URI. Cuando se encuentran sin codificar en un URI, se codifican por porcentaje. Cuando se encuentran codificados por porcentaje, se dejan como están.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones destinadas a versiones de .NET Framework a partir de la 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está habilitada de forma predeterminada. Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, la compatibilidad con los caracteres bidireccionales de Unicode está deshabilitada de forma predeterminada. Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=nameWithType>
