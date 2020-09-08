---
ms.openlocfilehash: 1487b5f47966cfcae0e47848dae99b39b42db18d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496403"
---
### <a name="keytips-behavior-improved-in-wpf"></a><span data-ttu-id="672db-101">Mejora del comportamiento de los KeyTip en WPF</span><span class="sxs-lookup"><span data-stu-id="672db-101">Keytips behavior improved in WPF</span></span>

#### <a name="details"></a><span data-ttu-id="672db-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="672db-102">Details</span></span>

<span data-ttu-id="672db-103">El comportamiento de los KeyTip se ha modificado para equipararlo al de Microsoft Word y el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="672db-103">Keytips behavior has been modified to bring parity with behavior on Microsoft Word and Windows Explorer.</span></span> <span data-ttu-id="672db-104">Mediante la comprobación de si el estado del KeyTip está habilitado o no cuando se presiona una <xref:System.Windows.Input.KeyEventArgs.SystemKey> (en concreto, <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF administra las teclas de KeyTip de la forma adecuada.</span><span class="sxs-lookup"><span data-stu-id="672db-104">By checking whether keytip state is enabled or not in the case of a <xref:System.Windows.Input.KeyEventArgs.SystemKey> (in particular, <xref:System.Windows.Input.Key> or <xref:System.Windows.Input.Key.F11>) being pressed, WPF handles keytip keys appropriately.</span></span> <span data-ttu-id="672db-105">Los KeyTip ahora cierran un menú incluso cuando se abre con el mouse.</span><span class="sxs-lookup"><span data-stu-id="672db-105">Keytips now dismiss a menu even when it is opened by mouse.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="672db-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="672db-106">Suggestion</span></span>

<span data-ttu-id="672db-107">N/D</span><span class="sxs-lookup"><span data-stu-id="672db-107">N/A</span></span>

| <span data-ttu-id="672db-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="672db-108">Name</span></span>    | <span data-ttu-id="672db-109">Valor</span><span class="sxs-lookup"><span data-stu-id="672db-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="672db-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="672db-110">Scope</span></span>   |<span data-ttu-id="672db-111">Borde</span><span class="sxs-lookup"><span data-stu-id="672db-111">Edge</span></span>|
|<span data-ttu-id="672db-112">Versión</span><span class="sxs-lookup"><span data-stu-id="672db-112">Version</span></span>|<span data-ttu-id="672db-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="672db-113">4.7.2</span></span>|
|<span data-ttu-id="672db-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="672db-114">Type</span></span>|<span data-ttu-id="672db-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="672db-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="672db-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="672db-116">Affected APIs</span></span>

<span data-ttu-id="672db-117">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="672db-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
