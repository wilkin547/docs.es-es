---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614689"
---
### <a name="changes-in-path-normalization"></a>Cambios en la normalización de la ruta de acceso

#### <a name="details"></a>Detalles

A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, ha cambiado la forma en que el entorno de ejecución normaliza las rutas de acceso. La normalización de una ruta de acceso implica la modificación de la cadena que identifica una ruta de acceso o un archivo para que se ajuste a una ruta de acceso válida en el sistema operativo de destino. La normalización implica normalmente:

- La canonicalización del componente y los separadores de directorios.
- La aplicación del directorio actual en una ruta de acceso relativa.
- La evaluación del directorio relativo (.) o el directorio principal (..) en una ruta de acceso.
- El recorte de caracteres especificados.
A partir de las aplicaciones que tienen como destino .NET Framework 4.6.2, los cambios siguientes en la normalización de la ruta de acceso están habilitados de forma predeterminada:
  - El tiempo de ejecución se aplaza para la función [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) del sistema operativo con el objetivo de normalizar las rutas de acceso.
- La normalización ya no implica el recorte del final de los segmentos de directorio (como el espacio al final de un nombre de directorio).
- Compatibilidad de la sintaxis de la ruta de acceso del dispositivo con plena confianza ( incluido `\\.\`) y, para las API de E/S del archivo en mscorlib.dll, `\\?\`.
- El tiempo de ejecución o valida las rutas de acceso de la sintaxis del dispositivo.
- Es compatible el uso de la sintaxis del dispositivo para obtener acceso a los flujos de datos alternativos.
Estos cambios mejoran el rendimiento a la vez que permiten a los métodos obtener acceso a las rutas de acceso a las que no se podía obtener acceso anteriormente. Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o posterior, no se ven afectadas por este cambio.

#### <a name="suggestion"></a>Sugerencia

Las aplicaciones que tienen como destino .NET Framework 4.6.2 o una versión posterior pueden rechazar este cambio y usar la normalización heredada si agregan lo siguiente a la sección `<runtime>` del archivo de configuración de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

Las aplicaciones que tienen como destino .NET Framework 4.6.1 o versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2 o versiones posteriores, pueden habilitar los cambios en la normalización de rutas de acceso si se agrega la línea siguiente a la sección `<runtime>` del archivo .configuration de la aplicación:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.6.2       |
| Tipo    | Redestinación |
