---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614970"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>WPF Cambio de una clave principal cuando se muestran datos ADO en un escenario principal-detalle

#### <a name="details"></a>Detalles

Supongamos que tiene una colección ADO de elementos del tipo `Order`, con una relación llamada &quot;OrderDetails&quot; que se relaciona con una colección de elementos del tipo `Detail` a través de la clave principal &quot;OrderID&quot;. En su aplicación WPF, puede enlazar un control de lista a los detalles de un pedido determinado:

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

donde DataContext es `Order`. WPF obtiene el valor de la propiedad `OrderDetails`: una colección D de todos los elementos `Detail` cuya `OrderID` coincide con la `OrderID` del elemento maestro. El cambio de comportamiento se produce cuando se cambia la clave principal `OrderID` del elemento maestro. ADO cambia automáticamente el `OrderID` de cada uno de los registros afectados en la colección Detalles (es decir, los que se copiaron en la colección D).  Pero, ¿qué ocurre con D?

- Comportamiento anterior: la colección D se borra. El elemento principal *no* genera una notificación de cambio para la propiedad `OrderDetails`. Listbox continúa usando la colección D, que ahora está vacía.
- Comportamiento nuevo:  la colección D no cambia. Cada uno de sus elementos genera una notificación de cambio para la propiedad `OrderID`. ListBox continúa usando la colección D, y muestra los detalles con el nuevo `OrderID`. WPF implementa el nuevo comportamiento mediante la creación de la colección D de una manera diferente: llamando al método ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con el argumento `followParent` establecido en `true`.

#### <a name="suggestion"></a>Sugerencia

Una aplicación obtiene el nuevo comportamiento mediante el siguiente modificador de AppContext.

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

El conmutador tiene como valor predeterminado `true` (comportamiento anterior) para las aplicaciones que tienen como destino .NET 4.7.1 o inferior, y `false` (nuevo comportamiento) para las aplicaciones que tienen como destino .NET 4.7.2 o posterior.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.7.2       |
| Tipo    | Redestinación |
