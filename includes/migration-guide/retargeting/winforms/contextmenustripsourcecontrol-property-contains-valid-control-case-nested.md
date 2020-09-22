---
ms.openlocfilehash: 5529b8379c5cb9f1bc525e0c2340f6b885e35822
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606953"
---
### <a name="contextmenustripsourcecontrol-property-contains-a-valid-control-in-the-case-of-nested-toolstripmenuitems"></a>La propiedad ContextMenuStrip.SourceControl contiene un control válido en el caso de controles ToolStripMenuItem anidados

#### <a name="details"></a>Detalles

En .NET Framework 4.7.1 y versiones anteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> devuelve NULL de forma incorrecta cuando el usuario abre el menú desde controles <xref:System.Windows.Forms.ToolStripMenuItem> anidados. En .NET Framework 4.7.2 y versiones posteriores, la propiedad <xref:System.Windows.Forms.ContextMenuStrip.SourceControl> siempre se establece en el control de origen real.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que una aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.2 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Tiene como destino .NET Framework 4.7.2. Este cambio está habilitado de forma predeterminada para las aplicaciones de Windows Forms destinadas a .NET Framework 4.7.2 o una versión posterior.
- Tiene como destino .NET Framework 4.7.1 o una versión anterior, y no participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](../../../../docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo app.config y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue=false"/>
</runtime>
```

En las aplicaciones destinadas a .NET Framework 4.7.2 o una versión posterior, y en las que se quiere conservar el comportamiento heredado, se puede participar en el uso del valor de control de origen heredado si se establece explícitamente este modificador de AppContext en `true`.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.7.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>
