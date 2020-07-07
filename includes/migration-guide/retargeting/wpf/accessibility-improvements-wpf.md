---
ms.openlocfilehash: 47d3829748deef2c7c3610816b8941bf88da7ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614925"
---
### <a name="accessibility-improvements-in-wpf"></a>Mejoras de accesibilidad en WPF

#### <a name="details"></a>Detalles

**Mejoras de contraste alto**
<ul><li>El foco para el control <xref:System.Windows.Controls.Expander> ahora es visible. En versiones anteriores de .NET Framework no lo tenía.
- Cuando se seleccionan los controles <xref:System.Windows.Controls.CheckBox> y <xref:System.Windows.Controls.RadioButton>, ahora el texto es más fácil de ver que en versiones anteriores de .NET Framework.
- El borde de un control <xref:System.Windows.Controls.ComboBox> deshabilitado ahora tiene el mismo color que el texto deshabilitado. En versiones anteriores de .NET Framework no lo tenía.
- Los botones deshabilitados y con el foco ahora usan el color de tema correcto. En versiones anteriores de .NET Framework no lo hacían.
- Ahora el botón de lista desplegable se ve cuando el estilo de un control <xref:System.Windows.Controls.ComboBox> se establece en <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey?displayProperty=nameWithType>. En versiones anteriores de .NET Framework no se veía.
- La flecha del indicador de ordenación en un control <xref:System.Windows.Controls.DataGrid> ahora usa los colores del tema. En versiones anteriores de .NET Framework no se usaban.
- El estilo de hipervínculo predeterminado cambia ahora al color de tema correcto al pasar el mouse. En versiones anteriores de .NET Framework no se usaban.
- El foco del teclado en los botones de radio ahora se ve. En versiones anteriores de .NET Framework no lo tenía.
- En la columna de casilla del control <xref:System.Windows.Controls.DataGrid> ahora se usan los colores esperados para los comentarios de foco de teclado. En versiones anteriores de .NET Framework no se usaban.
- Los objetos visuales de foco de teclado ahora se ven en los controles <xref:System.Windows.Controls.ComboBox> y <xref:System.Windows.Controls.ListBox>. En versiones anteriores de .NET Framework no lo tenía.</p>
**Mejoras en la interacción con el lector de pantalla**
<ul><li>Ahora los lectores de pantalla anuncian los controles <xref:System.Windows.Controls.Expander> correctamente como grupos (expandir o contraer).
Ahora los lectores de pantalla anuncian los controles - <xref:System.Windows.Controls.DataGridCell> correctamente como celdas de cuadrícula de datos (localizadas).
- Ahora los lectores de pantalla anunciarán el nombre de un control <xref:System.Windows.Controls.ComboBox> editable.
Los lectores de pantalla ya no anuncian los controles - <xref:System.Windows.Controls.PasswordBox> como &quot;no hay elemento a la vista&quot;.</p>
**Compatibilidad con LiveRegion** Los lectores de pantalla como Narrador ayudan a los usuarios a conocer el contenido de la interfaz de usuario de una aplicación, por lo general mediante la descripción sobre algo que tenga el foco en la interfaz de usuario, ya que probablemente sea el elemento de más interés para el usuario. Pero si un elemento de la interfaz de usuario cambia en alguna parte de la pantalla y no tiene el foco, puede que no se notifique al usuario y este pierda información importante. Las regiones activas están diseñadas para solucionar este problema. Un desarrollador puede usarlas para informar al lector de pantalla o a cualquier otro cliente de [UI Automation](~/docs/framework/ui-automation/ui-automation-overview.md) de que se ha realizado un cambio importante en un elemento de la interfaz de usuario. Luego el lector de pantalla puede decidir cómo y cuándo informar al usuario de este cambio. La propiedad LiveSetting también permite al lector de pantalla saber la importancia de informar al usuario de los cambios realizados en la interfaz de usuario.

#### <a name="suggestion"></a>Sugerencia

**Cómo participar o no en estos cambios** Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.7.1 o una versión posterior. La aplicación se puede beneficiar de estos cambios de cualquiera de las maneras siguientes:

- Establecer .NET Framework 4.7.1 como destino. Éste es el enfoque recomendado. Estos cambios de accesibilidad están habilitados de forma predeterminada para las aplicaciones de WPF destinadas a .NET Framework 4.7.1 o una versión posterior.
- No participa en los comportamientos de accesibilidad heredados mediante la adición del [modificador de AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) siguiente a la sección `<runtime>` del archivo de configuración de la aplicación y estableciéndolo en `false`, como se muestra en el ejemplo siguiente.

<pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

En las aplicaciones destinadas a .NET Framework 4.7.1 o una versión posterior, y en las que se quiere conservar el comportamiento de accesibilidad heredado, se puede participar en el uso de las características de accesibilidad heredadas si se establece explícitamente este modificador de AppContext en `true`.
Para obtener información general de la automatización de la interfaz de usuario, vea la [información general sobre la Automatización de la interfaz de usuario](~/docs/framework/ui-automation/ui-automation-overview.md).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Major       |
| Versión | 4.7.1       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LiveRegionChangedEvent?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationLiveSetting?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.LiveSettingProperty?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.SetLiveSetting(System.Windows.DependencyObject,System.Windows.Automation.AutomationLiveSetting)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.AutomationProperties.GetLiveSetting(System.Windows.DependencyObject)?displayProperty=nameWithType>
- <xref:System.Windows.Automation.Peers.AutomationPeer.GetLiveSettingCore?displayProperty=nameWithType>
