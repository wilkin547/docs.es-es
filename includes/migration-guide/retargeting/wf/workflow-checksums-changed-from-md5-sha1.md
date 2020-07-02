---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614841"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Las sumas de comprobación de flujo de trabajo han cambiado de MD5 a SHA1

#### <a name="details"></a>Detalles

Para admitir la depuración con Visual Studio, el tiempo de ejecución de flujo de trabajo genera una suma de comprobación para una instancia de flujo de trabajo mediante un algoritmo de hash. En .NET Framework 4.6.2 y versiones anteriores, el hash de suma de comprobación de flujo de trabajo usaba el algoritmo MD5, que causaba problemas en sistemas compatibles con FIPS. A partir de .NET Framework 4.7, el algoritmo es SHA1. Si se han conservado estas sumas de comprobación en el código, serán incompatibles.

#### <a name="suggestion"></a>Sugerencia

Si el código no puede cargar las instancias de flujo de trabajo debido a un error de suma de comprobación, pruebe a establecer el modificador `AppContext`&quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; en true. En el código:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

O bien, en la configuración:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7         |
| Tipo    | Redestinación |
