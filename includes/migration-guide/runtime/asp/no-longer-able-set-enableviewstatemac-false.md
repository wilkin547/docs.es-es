---
ms.openlocfilehash: cecb7b2abd4f57fdaacb0ea373cc19dc3cd9b24a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620542"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="b811b-101">Ya no se puede establecer EnableViewStateMac en false</span><span class="sxs-lookup"><span data-stu-id="b811b-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="b811b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b811b-102">Details</span></span>

<span data-ttu-id="b811b-103">ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="b811b-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="b811b-104">El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado.</span><span class="sxs-lookup"><span data-stu-id="b811b-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="b811b-105">Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="b811b-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b811b-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b811b-106">Suggestion</span></span>

<span data-ttu-id="b811b-107">Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).</span><span class="sxs-lookup"><span data-stu-id="b811b-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="b811b-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b811b-108">Name</span></span>    | <span data-ttu-id="b811b-109">Valor</span><span class="sxs-lookup"><span data-stu-id="b811b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b811b-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b811b-110">Scope</span></span>   |<span data-ttu-id="b811b-111">Major</span><span class="sxs-lookup"><span data-stu-id="b811b-111">Major</span></span>|
|<span data-ttu-id="b811b-112">Versión</span><span class="sxs-lookup"><span data-stu-id="b811b-112">Version</span></span>|<span data-ttu-id="b811b-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b811b-113">4.5.2</span></span>|
|<span data-ttu-id="b811b-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="b811b-114">Type</span></span>|<span data-ttu-id="b811b-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b811b-115">Runtime</span></span>|
