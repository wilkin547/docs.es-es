---
ms.openlocfilehash: 43e9c1c2f03daedf4d56152da5672b89399a3c69
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804683"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="4de5e-101">VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows</span><span class="sxs-lookup"><span data-stu-id="4de5e-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4de5e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4de5e-102">Details</span></span>|<span data-ttu-id="4de5e-103">A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales.</span><span class="sxs-lookup"><span data-stu-id="4de5e-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="4de5e-104">Por ejemplo, se producirá un error al hacer referencia a <code>Windows.Forms.DialogResult</code>.</span><span class="sxs-lookup"><span data-stu-id="4de5e-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="4de5e-105">En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="4de5e-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="4de5e-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4de5e-106">Suggestion</span></span>|<span data-ttu-id="4de5e-107">Debería actualizarse el código para hacer referencia a las API <code>System.Windows</code> con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.</span><span class="sxs-lookup"><span data-stu-id="4de5e-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="4de5e-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4de5e-108">Scope</span></span>|<span data-ttu-id="4de5e-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="4de5e-109">Minor</span></span>|
|<span data-ttu-id="4de5e-110">Versión</span><span class="sxs-lookup"><span data-stu-id="4de5e-110">Version</span></span>|<span data-ttu-id="4de5e-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="4de5e-111">4.5.2</span></span>|
|<span data-ttu-id="4de5e-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="4de5e-112">Type</span></span>|<span data-ttu-id="4de5e-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4de5e-113">Retargeting</span></span>|

