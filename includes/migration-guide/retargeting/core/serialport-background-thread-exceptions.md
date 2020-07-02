---
ms.openlocfilehash: e66a5c2a33a4ab5cf35013c1843936ffd01f90a2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614749"
---
### <a name="serialport-background-thread-exceptions"></a>Excepciones de subprocesos en segundo plano SerialPort

#### <a name="details"></a>Detalles

Los subprocesos en segundo plano creados con secuencias <xref:System.IO.Ports.SerialPort> ya no finalizan el proceso cuando se inician excepciones del sistema operativo. <br/>En las aplicaciones destinadas a .NET Framework 4.7 y versiones anteriores, un proceso se termina cuando se inicia una excepción del sistema operativo en un subproceso en segundo plano creado con una secuencia <xref:System.IO.Ports.SerialPort>. <br/>En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, los subprocesos en segundo plano esperan eventos del sistema operativo relacionados con el puerto serie activo y pueden dejar de funcionar en algunos casos, como la eliminación repentina del puerto serie.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones que tienen como destino .NET Framework 4.7.1, se puede rechazar el control de excepciones si no es adecuado si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true" />
</runtime>
```

Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.7.1 o versiones posteriores, se puede incluir el control de excepciones si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
