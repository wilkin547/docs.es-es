---
ms.openlocfilehash: 5f1a8af37a305ab0904801002dd99e17e8eca62e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616127"
---
### <a name="two-way-data-binding-to-a-property-with-a-non-public-setter-is-not-supported"></a><span data-ttu-id="3de6d-101">No se admite el enlace de datos bidireccional a una propiedad con un establecedor no público</span><span class="sxs-lookup"><span data-stu-id="3de6d-101">Two-way data-binding to a property with a non-public setter is not supported</span></span>

#### <a name="details"></a><span data-ttu-id="3de6d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3de6d-102">Details</span></span>

<span data-ttu-id="3de6d-103">Nunca se ha admitido el escenario de tratar de enlazar datos a una propiedad sin establecedor público.</span><span class="sxs-lookup"><span data-stu-id="3de6d-103">Attempting to data bind to a property without a public setter has never been a supported scenario.</span></span> <span data-ttu-id="3de6d-104">A partir de .NET Framework 4.5.1, este escenario iniciará una excepción <xref:System.InvalidOperationException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="3de6d-104">Beginning in the .NET Framework 4.5.1, this scenario will throw an <xref:System.InvalidOperationException?displayProperty=fullName>.</span></span> <span data-ttu-id="3de6d-105">Tenga en cuenta que esta nueva excepción solo se iniciará para aquellas aplicaciones que tengan .NET Framework 4.5.1 como destino específico.</span><span class="sxs-lookup"><span data-stu-id="3de6d-105">Note that this new exception will only be thrown for apps that specifically target the .NET Framework 4.5.1.</span></span> <span data-ttu-id="3de6d-106">Si una aplicación tiene como destino .NET Framework 4.5, se permitirá la llamada.</span><span class="sxs-lookup"><span data-stu-id="3de6d-106">If an app targets the .NET Framework 4.5, the call will be allowed.</span></span> <span data-ttu-id="3de6d-107">Si la aplicación no tiene como destino ninguna versión concreta de .NET Framework, el enlace se tratará como unidireccional.</span><span class="sxs-lookup"><span data-stu-id="3de6d-107">If the app does not target a particular .NET Framework version, the binding will be treated as one-way.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3de6d-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3de6d-108">Suggestion</span></span>

<span data-ttu-id="3de6d-109">Debería actualizarse la aplicación para utilizar un enlace bidireccional, o bien para exponer públicamente el establecedor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="3de6d-109">The app should be updated to either use one-way binding, or expose the property's setter publicly.</span></span> <span data-ttu-id="3de6d-110">También es posible establecer .NET Framework 4.5 como destino para que la aplicación presente el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="3de6d-110">Alternatively, targeting the .NET Framework 4.5 will cause the app to exhibit the old behavior.</span></span>

| <span data-ttu-id="3de6d-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3de6d-111">Name</span></span>    | <span data-ttu-id="3de6d-112">Valor</span><span class="sxs-lookup"><span data-stu-id="3de6d-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3de6d-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3de6d-113">Scope</span></span>   | <span data-ttu-id="3de6d-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="3de6d-114">Minor</span></span>       |
| <span data-ttu-id="3de6d-115">Versión</span><span class="sxs-lookup"><span data-stu-id="3de6d-115">Version</span></span> | <span data-ttu-id="3de6d-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="3de6d-116">4.5.1</span></span>       |
| <span data-ttu-id="3de6d-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="3de6d-117">Type</span></span>    | <span data-ttu-id="3de6d-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="3de6d-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3de6d-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3de6d-119">Affected APIs</span></span>

- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>
