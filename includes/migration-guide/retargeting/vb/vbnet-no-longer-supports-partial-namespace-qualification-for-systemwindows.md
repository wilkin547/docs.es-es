---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804683"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="a7e20-101">VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows</span><span class="sxs-lookup"><span data-stu-id="a7e20-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a7e20-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7e20-102">Details</span></span>|<span data-ttu-id="a7e20-103">A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales.</span><span class="sxs-lookup"><span data-stu-id="a7e20-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="a7e20-104">Por ejemplo, se producirá un error al hacer referencia a <code>Windows.Forms.DialogResult</code>.</span><span class="sxs-lookup"><span data-stu-id="a7e20-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="a7e20-105">En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="a7e20-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="a7e20-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a7e20-106">Suggestion</span></span>|<span data-ttu-id="a7e20-107">Debería actualizarse el código para hacer referencia a las API <code>System.Windows</code> con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.</span><span class="sxs-lookup"><span data-stu-id="a7e20-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="a7e20-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a7e20-108">Scope</span></span>|<span data-ttu-id="a7e20-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a7e20-109">Minor</span></span>|
|<span data-ttu-id="a7e20-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a7e20-110">Version</span></span>|<span data-ttu-id="a7e20-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a7e20-111">4.5.2</span></span>|
|<span data-ttu-id="a7e20-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a7e20-112">Type</span></span>|<span data-ttu-id="a7e20-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="a7e20-113">Retargeting</span></span>|
