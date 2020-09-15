---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616072"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="70429-101">VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows</span><span class="sxs-lookup"><span data-stu-id="70429-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

#### <a name="details"></a><span data-ttu-id="70429-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="70429-102">Details</span></span>

<span data-ttu-id="70429-103">A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales.</span><span class="sxs-lookup"><span data-stu-id="70429-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="70429-104">Por ejemplo, se producirá un error al hacer referencia a `Windows.Forms.DialogResult`.</span><span class="sxs-lookup"><span data-stu-id="70429-104">For example, referring to `Windows.Forms.DialogResult` will fail.</span></span> <span data-ttu-id="70429-105">En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="70429-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="70429-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="70429-106">Suggestion</span></span>

<span data-ttu-id="70429-107">Debería actualizarse el código para hacer referencia a las API `System.Windows` con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.</span><span class="sxs-lookup"><span data-stu-id="70429-107">Code should be updated to refer to `System.Windows` APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>

| <span data-ttu-id="70429-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="70429-108">Name</span></span>    | <span data-ttu-id="70429-109">Valor</span><span class="sxs-lookup"><span data-stu-id="70429-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="70429-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="70429-110">Scope</span></span>   | <span data-ttu-id="70429-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="70429-111">Minor</span></span>       |
| <span data-ttu-id="70429-112">Versión</span><span class="sxs-lookup"><span data-stu-id="70429-112">Version</span></span> | <span data-ttu-id="70429-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="70429-113">4.5.2</span></span>       |
| <span data-ttu-id="70429-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="70429-114">Type</span></span>    | <span data-ttu-id="70429-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="70429-115">Retargeting</span></span> |
