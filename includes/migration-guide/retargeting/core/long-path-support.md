---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614713"
---
### <a name="long-path-support"></a>Compatibilidad con rutas de acceso con formato largo

#### <a name="details"></a>Detalles

A partir de las aplicaciones destinadas a .NET Framework 4.6.2, se admiten las rutas de acceso largas (de hasta 32 000 caracteres) y se ha quitado la limitación de 260 caracteres (o `MAX_PATH`) para las longitudes de ruta de acceso. Para las aplicaciones que se vuelven a compilar para .NET Framework 4.6.2, las rutas de acceso de código que antes iniciaban una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> porque una ruta de acceso superaba los 260 caracteres ahora iniciarán una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> solo en las condiciones siguientes:

- La longitud de la ruta de acceso es mayor que <xref:System.Int16.MaxValue> (32 767) caracteres.
- El sistema operativo devuelve `COR_E_PATHTOOLONG` o su equivalente.
Para las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, el entorno de ejecución inicia automáticamente una excepción <xref:System.IO.PathTooLongException?displayProperty=fullName> cada vez que una ruta de acceso supera los 260 caracteres.

#### <a name="suggestion"></a>Sugerencia

Para las aplicaciones que tienen como destino .NET Framework 4.6.2, se puede rechazar la compatibilidad con rutas de acceso largas si no es adecuada si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

Para las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, se puede incluir la compatibilidad con rutas de acceso largas si se agrega lo siguiente a la sección `<runtime>` del archivo `app.config`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.2       |
| Tipo    | Redestinación |
