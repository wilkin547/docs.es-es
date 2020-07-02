---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614680"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>Mejoras de accesibilidad de ASP.NET en .NET Framework 4.7.1

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.7.1, ASP.NET ha mejorado el funcionamiento de los controles web de ASP.NET con la tecnología de accesibilidad en Visual Studio para una mejor compatibilidad con los clientes de ASP.NET.  Entre otros, se incluyen los cambios siguientes:

- Cambios para implementar patrones de accesibilidad de interfaz de usuario que faltan en los controles, como el cuadro de diálogo Agregar campo en el Asistente para vistas de detalles o el cuadro de diálogo Configurar ListView del Asistente de ListView.
- Cambios para mejorar la presentación en el modo Contraste alto, como el Editor de campos del elemento de paginación de datos.
- Cambios para mejorar las experiencias de navegación del teclado para los controles, como el cuadro de diálogo Campos del Asistente para editar campos del elemento de paginación del control DataPager, el cuadro de diálogo Configurar ObjectContext o el cuadro de diálogo Configurar selección de datos del Asistente para configurar origen de datos.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que el diseñador de Visual Studio se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.1 o una versión posterior. La aplicación web se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Instalar Visual Studio 2017 15.3 o una versión posterior, que es compatible con las nuevas características de accesibilidad con el modificador siguiente de AppContext de forma predeterminada.
- No participar en los comportamientos de accesibilidad heredados agregando el modificador de AppContext `Switch.UseLegacyAccessibilityFeatures` a la sección `<runtime>` del archivo devenv.exe.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |
