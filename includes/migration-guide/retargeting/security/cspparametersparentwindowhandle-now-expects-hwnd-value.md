---
ms.openlocfilehash: 4b5c886ad35afbbf0a68e03b3174ab9ea1f5524f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614764"
---
### <a name="cspparametersparentwindowhandle-now-expects-hwnd-value"></a>CspParameters.ParentWindowHandle espera ahora el valor HWND

#### <a name="details"></a>Detalles

El valor <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle>, introducido en .NET Framework 2.0, permite que una aplicación registre un valor de identificador de ventana principal, de modo que cualquier interfaz de usuario necesaria para tener acceso a la clave (por ejemplo, una solicitud del PIN o un cuadro de diálogo de consentimiento) se abra como elemento secundario modal de la ventana especificada. A partir de las aplicaciones destinadas a .NET Framework 4.7, una aplicación de Windows Forms puede establecer la propiedad <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle> con código similar al siguiente:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

En versiones anteriores de .NET Framework, se esperaba que el valor fuera un <xref:System.IntPtr?displayProperty=fullName> que representara una ubicación en memoria donde se encontraba el valor [HWND](https://docs.microsoft.com/windows/desktop/WinProg/windows-data-types#HWND). Establecer la propiedad en form.Handle no tenía ningún efecto en Windows 7 y versiones anteriores, pero en Windows 8 y versiones posteriores, da como resultado &quot;<xref:System.Security.Cryptography.CryptographicException?displayProperty=fullName>: El parámetro no es correcto&quot;.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones destinadas a .NET Framework 4.7 o versiones posteriores que quieran registrar una relación de ventana principal, se recomienda usar la forma simplificada:

```csharp
cspParameters.ParentWindowHandle = form.Handle;
```

Los usuarios que hayan identificado que el valor correcto para pasar era la dirección de una ubicación de memoria que contenía el valor `form.Handle`, pueden rechazar este cambio de comportamiento si establecen el modificador de AppContext `Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle` en `true`:

- Configurando mediante programación los modificadores de compatibilidad en AppContext, como se explica [aquí](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).
- Agregando la siguiente línea a la sección `<runtime>` del archivo app.config:

```xml
<runtime>
 <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.DoNotAddrOfCspParentWindowHandle=true"/>
</runtime>
```

En cambio, los usuarios que quieran incluir el comportamiento nuevo en el entorno de ejecución de .NET Framework 4.7 cuando la aplicación se carga bajo versiones anteriores de .NET Framework, pueden establecer el modificador de AppContext en `false`.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7         |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Security.Cryptography.CspParameters.ParentWindowHandle?displayProperty=nameWithType>
