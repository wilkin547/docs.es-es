---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614665"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a>Asegurarse de que System.Uri usa un juego de caracteres reservados coherente

#### <a name="details"></a>Detalles

En <xref:System.Uri?displayProperty=fullName>, algunos caracteres codificados por porcentaje que en ocasiones se descodificaban ahora se dejan sin codificar de manera constante. Esto se produce en las propiedades y métodos que tienen acceso a los componentes de ruta de acceso, consulta, fragmento o información de usuario del URI. El comportamiento solo cambiará cuando se cumplen las dos acciones siguientes:

- El URI contiene el formato codificado de cualquiera de los caracteres reservados siguientes: `:`, `'`, `(`, `)`, `!` o `*`.
- El URI contiene un carácter no reservado codificado o Unicode. Si se cumplen las dos condiciones anteriores, los caracteres reservados codificados se dejan codificados. En versiones anteriores de .NET Framework se descodificaban.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones destinadas a versiones de .NET Framework a partir de 4.7.2, el nuevo comportamiento de descodificación está habilitado de forma predeterminada. Si no quiere este cambio, puede deshabilitarlo mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

Para las aplicaciones destinadas a versiones anteriores de .NET Framework pero que se ejecutan en versiones a partir de .NET Framework 4.7.2, el comportamiento de descodificación nuevo está deshabilitado de forma predeterminada. Puede habilitarla mediante la adición del modificador [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Uri?displayProperty=nameWithType>
