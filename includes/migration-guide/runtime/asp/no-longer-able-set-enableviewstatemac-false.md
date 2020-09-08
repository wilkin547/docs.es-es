---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497706"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="06920-101">Ya no se puede establecer EnableViewStateMac en false</span><span class="sxs-lookup"><span data-stu-id="06920-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="06920-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="06920-102">Details</span></span>

<span data-ttu-id="06920-103">ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="06920-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="06920-104">El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado.</span><span class="sxs-lookup"><span data-stu-id="06920-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="06920-105">Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="06920-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="06920-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="06920-106">Suggestion</span></span>

<span data-ttu-id="06920-107">Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).</span><span class="sxs-lookup"><span data-stu-id="06920-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="06920-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="06920-108">Name</span></span>    | <span data-ttu-id="06920-109">Valor</span><span class="sxs-lookup"><span data-stu-id="06920-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="06920-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="06920-110">Scope</span></span>   |<span data-ttu-id="06920-111">Major</span><span class="sxs-lookup"><span data-stu-id="06920-111">Major</span></span>|
|<span data-ttu-id="06920-112">Versión</span><span class="sxs-lookup"><span data-stu-id="06920-112">Version</span></span>|<span data-ttu-id="06920-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="06920-113">4.5.2</span></span>|
|<span data-ttu-id="06920-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="06920-114">Type</span></span>|<span data-ttu-id="06920-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="06920-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="06920-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="06920-116">Affected APIs</span></span>

<span data-ttu-id="06920-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="06920-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
