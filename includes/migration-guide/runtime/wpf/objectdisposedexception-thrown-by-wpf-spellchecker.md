---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497304"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="f8534-101">El corrector ortográfico de WPF inicia la excepción ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="f8534-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="f8534-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f8534-102">Details</span></span>

<span data-ttu-id="f8534-103">En ocasiones, las aplicaciones de WPF se bloquean durante el cierre de la aplicación y el corrector ortográfico inicia una excepción <xref:System.ObjectDisposedException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f8534-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="f8534-104">Esto se ha corregido en WPF de .NET Framework 4.7 mediante el control correcto de la excepción, lo que garantiza que las aplicaciones ya no se ven afectadas de manera negativa.</span><span class="sxs-lookup"><span data-stu-id="f8534-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="f8534-105">Debe tenerse en cuenta que se pueden seguir observando primeras excepciones ocasionales en las aplicaciones que se ejecutan con un depurador.</span><span class="sxs-lookup"><span data-stu-id="f8534-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f8534-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f8534-106">Suggestion</span></span>

<span data-ttu-id="f8534-107">Actualizar a .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f8534-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="f8534-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f8534-108">Name</span></span>    | <span data-ttu-id="f8534-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f8534-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f8534-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f8534-110">Scope</span></span>   |<span data-ttu-id="f8534-111">Borde</span><span class="sxs-lookup"><span data-stu-id="f8534-111">Edge</span></span>|
|<span data-ttu-id="f8534-112">Versión</span><span class="sxs-lookup"><span data-stu-id="f8534-112">Version</span></span>|<span data-ttu-id="f8534-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f8534-113">4.6.1</span></span>|
|<span data-ttu-id="f8534-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="f8534-114">Type</span></span>|<span data-ttu-id="f8534-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f8534-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f8534-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f8534-116">Affected APIs</span></span>

<span data-ttu-id="f8534-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="f8534-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
