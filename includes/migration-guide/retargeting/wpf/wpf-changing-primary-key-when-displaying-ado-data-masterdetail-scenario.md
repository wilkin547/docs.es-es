---
ms.openlocfilehash: 2cd107dc92fd0fae89717c38840ce7ea44f3ac9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234003"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>WPF Cambio de una clave principal cuando se muestran datos ADO en un escenario principal-detalle

|   |   |
|---|---|
|Detalles|Supongamos que tiene una colección ADO de elementos del tipo <code>Order</code>, con una relación llamada &quot;OrderDetails&quot; que se relaciona con una colección de elementos del tipo <code>Detail</code> a través de la clave principal &quot;OrderID&quot;. En su aplicación WPF, puede enlazar un control de lista a los detalles de un pedido determinado:<pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre>donde DataContext es <code>Order</code>. WPF obtiene el valor de la propiedad <code>OrderDetails</code>, una colección D de todos los elementos <code>Detail</code> cuyo <code>OrderID</code> coincide con el <code>OrderID</code> del elemento principal. El cambio de comportamiento surge cuando cambia la clave principal <code>OrderID</code> del elemento principal. ADO cambia automáticamente el <code>OrderID</code> de cada uno de los registros afectados en la colección Detalles (es decir, los que se copiaron en la colección D).  Pero, ¿qué ocurre con D?<ul><li>Comportamiento anterior:   la colección D se borra.   El elemento principal <em>no</em> genera una notificación de cambio para la propiedad <code>OrderDetails</code>.  Listbox continúa usando la colección D, que ahora está vacía.</li><li>Comportamiento nuevo:  la colección D no cambia.   Cada uno de sus elementos genera una notificación de cambio para la propiedad <code>OrderID</code>.  ListBox continúa usando la colección D, y muestra los detalles con el nuevo <code>OrderID</code>.</li></ul>WPF implementa el nuevo comportamiento mediante la creación de la colección D de una manera diferente: llamando al método ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con el argumento <code>followParent</code> establecido en <code>true</code>.|
|Sugerencia|Una aplicación obtiene el nuevo comportamiento mediante el siguiente modificador de AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre>El conmutador tiene como valor predeterminado <code>true</code> (comportamiento anterior) para las aplicaciones que tienen como destino .NET 4.7.1 o inferior, y <code>false</code> (nuevo comportamiento) para las aplicaciones que tienen como destino .NET 4.7.2 o posterior.|
|Ámbito|Secundaria|
|Versión|4.7.2|
|Tipo|Redestinación|
