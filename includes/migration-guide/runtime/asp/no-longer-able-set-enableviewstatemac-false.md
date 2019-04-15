---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236666"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="ba949-101">Ya no se puede establecer EnableViewStateMac en false</span><span class="sxs-lookup"><span data-stu-id="ba949-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ba949-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ba949-102">Details</span></span>|<span data-ttu-id="ba949-103">ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="ba949-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="ba949-104">El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado.</span><span class="sxs-lookup"><span data-stu-id="ba949-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="ba949-105">Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="ba949-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="ba949-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ba949-106">Suggestion</span></span>|<span data-ttu-id="ba949-107">Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).</span><span class="sxs-lookup"><span data-stu-id="ba949-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="ba949-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ba949-108">Scope</span></span>|<span data-ttu-id="ba949-109">Major</span><span class="sxs-lookup"><span data-stu-id="ba949-109">Major</span></span>|
|<span data-ttu-id="ba949-110">Versión</span><span class="sxs-lookup"><span data-stu-id="ba949-110">Version</span></span>|<span data-ttu-id="ba949-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ba949-111">4.5.2</span></span>|
|<span data-ttu-id="ba949-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="ba949-112">Type</span></span>|<span data-ttu-id="ba949-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="ba949-113">Runtime</span></span>|
