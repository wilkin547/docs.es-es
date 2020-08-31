---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558014"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="d9bc5-101">System.Security.Cryptography.Oid es funcionalmente de solo inicialización</span><span class="sxs-lookup"><span data-stu-id="d9bc5-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="d9bc5-102">La clase <xref:System.Security.Cryptography.Oid?displayProperty=fullName>, que se usa para representar valores de identificador de objeto ASN.1 y sus nombres "descriptivos", antes era completamente mutable.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="d9bc5-103">Esta mutabilidad se solía pasar por alto o aparecía por sorpresa.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="d9bc5-104">Los establecedores de propiedades ahora inician <xref:System.PlatformNotSupportedException> cuando se intenta cambiar el valor después de haberlo asignado.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d9bc5-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d9bc5-105">Change description</span></span>

<span data-ttu-id="d9bc5-106">En versiones anteriores, los establecedores de propiedades en <xref:System.Security.Cryptography.Oid> se pueden usar para cambiar el valor de las propiedades <xref:System.Security.Cryptography.Oid.FriendlyName> y <xref:System.Security.Cryptography.Oid.Value>.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="d9bc5-107">En .NET 5.0 y versiones posteriores, los establecedores de propiedad solo se pueden usar para inicializar el valor.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="d9bc5-108">Una vez que la propiedad tiene un valor, ya sea desde un constructor o una llamada anterior al establecedor de propiedades, dicho establecedor de propiedades siempre inicia <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d9bc5-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="d9bc5-109">Reason for change</span></span>

<span data-ttu-id="d9bc5-110">Este cambio permite reutilizar objetos <xref:System.Security.Cryptography.Oid> como parte de los valores devueltos en las API públicas para reducir los perfiles de asignación de objetos.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="d9bc5-111">Evita la necesidad de crear copias "defensivas" temporales cuando se usan valores <xref:System.Security.Cryptography.Oid> como entradas.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9bc5-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d9bc5-112">Version introduced</span></span>

<span data-ttu-id="d9bc5-113">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="d9bc5-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9bc5-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d9bc5-114">Recommended action</span></span>

<span data-ttu-id="d9bc5-115">Evite el uso de los establecedores de propiedades <xref:System.Security.Cryptography.Oid> que no sean para la inicialización de objetos.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="d9bc5-116">Para representar un nuevo valor, use una nueva instancia en lugar de cambiar el valor en un objeto existente.</span><span class="sxs-lookup"><span data-stu-id="d9bc5-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="d9bc5-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="d9bc5-117">Category</span></span>

<span data-ttu-id="d9bc5-118">Criptografía</span><span class="sxs-lookup"><span data-stu-id="d9bc5-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9bc5-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d9bc5-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
