---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803191"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="18f31-101">Ya no se puede establecer EnableViewStateMac en false</span><span class="sxs-lookup"><span data-stu-id="18f31-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="18f31-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="18f31-102">Details</span></span>|<span data-ttu-id="18f31-103">ASP.NET ya no permite a los desarrolladores especificar <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> o <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span><span class="sxs-lookup"><span data-stu-id="18f31-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="18f31-104">El código de autenticación de mensajes (MAC) de estado de vista ahora es obligatorio para todas las solicitudes con estado de vista integrado.</span><span class="sxs-lookup"><span data-stu-id="18f31-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="18f31-105">Solo afecta a las aplicaciones en las que la propiedad EnableViewStateMac esté establecida específicamente en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="18f31-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="18f31-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="18f31-106">Suggestion</span></span>|<span data-ttu-id="18f31-107">Se debe suponer que EnableViewStateMac se establece en true y se debe resolver cualquier error de MAC resultante (como se explica en [esta guía](https://support.microsoft.com/kb/2915218), que contiene varias resoluciones en función de la causa específica de los errores de MAC).</span><span class="sxs-lookup"><span data-stu-id="18f31-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="18f31-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="18f31-108">Scope</span></span>|<span data-ttu-id="18f31-109">Major</span><span class="sxs-lookup"><span data-stu-id="18f31-109">Major</span></span>|
|<span data-ttu-id="18f31-110">Versión</span><span class="sxs-lookup"><span data-stu-id="18f31-110">Version</span></span>|<span data-ttu-id="18f31-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="18f31-111">4.5.2</span></span>|
|<span data-ttu-id="18f31-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="18f31-112">Type</span></span>|<span data-ttu-id="18f31-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="18f31-113">Runtime</span></span>|
