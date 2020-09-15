---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614970"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="40191-101">WPF Cambio de una clave principal cuando se muestran datos ADO en un escenario principal-detalle</span><span class="sxs-lookup"><span data-stu-id="40191-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="40191-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="40191-102">Details</span></span>

<span data-ttu-id="40191-103">Supongamos que tiene una colección ADO de elementos del tipo `Order`, con una relación llamada &quot;OrderDetails&quot; que se relaciona con una colección de elementos del tipo `Detail` a través de la clave principal &quot;OrderID&quot;.</span><span class="sxs-lookup"><span data-stu-id="40191-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="40191-104">En su aplicación WPF, puede enlazar un control de lista a los detalles de un pedido determinado:</span><span class="sxs-lookup"><span data-stu-id="40191-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="40191-105">donde DataContext es `Order`.</span><span class="sxs-lookup"><span data-stu-id="40191-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="40191-106">WPF obtiene el valor de la propiedad `OrderDetails`: una colección D de todos los elementos `Detail` cuya `OrderID` coincide con la `OrderID` del elemento maestro.</span><span class="sxs-lookup"><span data-stu-id="40191-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="40191-107">El cambio de comportamiento se produce cuando se cambia la clave principal `OrderID` del elemento maestro.</span><span class="sxs-lookup"><span data-stu-id="40191-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="40191-108">ADO cambia automáticamente el `OrderID` de cada uno de los registros afectados en la colección Detalles (es decir, los que se copiaron en la colección D).</span><span class="sxs-lookup"><span data-stu-id="40191-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="40191-109">Pero, ¿qué ocurre con D?</span><span class="sxs-lookup"><span data-stu-id="40191-109">But what happens to D?</span></span>

- <span data-ttu-id="40191-110">Comportamiento anterior: la colección D se borra.</span><span class="sxs-lookup"><span data-stu-id="40191-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="40191-111">El elemento principal *no* genera una notificación de cambio para la propiedad `OrderDetails`.</span><span class="sxs-lookup"><span data-stu-id="40191-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="40191-112">Listbox continúa usando la colección D, que ahora está vacía.</span><span class="sxs-lookup"><span data-stu-id="40191-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="40191-113">Comportamiento nuevo:  la colección D no cambia.</span><span class="sxs-lookup"><span data-stu-id="40191-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="40191-114">Cada uno de sus elementos genera una notificación de cambio para la propiedad `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="40191-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="40191-115">ListBox continúa usando la colección D, y muestra los detalles con el nuevo `OrderID`.</span><span class="sxs-lookup"><span data-stu-id="40191-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="40191-116">WPF implementa el nuevo comportamiento mediante la creación de la colección D de una manera diferente: llamando al método ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con el argumento `followParent` establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="40191-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="40191-117">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="40191-117">Suggestion</span></span>

<span data-ttu-id="40191-118">Una aplicación obtiene el nuevo comportamiento mediante el siguiente modificador de AppContext.</span><span class="sxs-lookup"><span data-stu-id="40191-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="40191-119">El conmutador tiene como valor predeterminado `true` (comportamiento anterior) para las aplicaciones que tienen como destino .NET 4.7.1 o inferior, y `false` (nuevo comportamiento) para las aplicaciones que tienen como destino .NET 4.7.2 o posterior.</span><span class="sxs-lookup"><span data-stu-id="40191-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="40191-120">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="40191-120">Name</span></span>    | <span data-ttu-id="40191-121">Valor</span><span class="sxs-lookup"><span data-stu-id="40191-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="40191-122">Ámbito</span><span class="sxs-lookup"><span data-stu-id="40191-122">Scope</span></span>   | <span data-ttu-id="40191-123">Secundaria</span><span class="sxs-lookup"><span data-stu-id="40191-123">Minor</span></span>       |
| <span data-ttu-id="40191-124">Versión</span><span class="sxs-lookup"><span data-stu-id="40191-124">Version</span></span> | <span data-ttu-id="40191-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="40191-125">4.7.2</span></span>       |
| <span data-ttu-id="40191-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="40191-126">Type</span></span>    | <span data-ttu-id="40191-127">Redestinación</span><span class="sxs-lookup"><span data-stu-id="40191-127">Retargeting</span></span> |
