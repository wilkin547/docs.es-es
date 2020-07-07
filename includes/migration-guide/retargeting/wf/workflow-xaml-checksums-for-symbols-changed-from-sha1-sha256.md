---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616293"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Sumas de comprobación de flujo de trabajo XAML para los símbolos que se han cambiado de SHA1 a SHA256

#### <a name="details"></a>Detalles

Para admitir la depuración con Visual Studio, el tiempo de ejecución de flujo de trabajo genera una suma de comprobación para un archivo XAML de flujo de trabajo mediante un algoritmo de hash. En .NET Framework 4.6.2 y versiones anteriores, el hash de suma de comprobación de flujo de trabajo usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS. A partir de .NET Framework 4.7, el algoritmo predeterminado se ha cambiado a SHA1. A partir de .NET Framework 4.8, el algoritmo predeterminado se ha cambiado a SHA256.

#### <a name="suggestion"></a>Sugerencia

Si el código no puede cargar las instancias de flujo de trabajo o no puede buscar símbolos adecuados debido a un error de suma de comprobación, pruebe a establecer el valor `AppContext` "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" en `true`. Mediante código:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

O bien, en la configuración:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.8         |
| Tipo    | Redestinación |
