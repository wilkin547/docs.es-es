---
ms.openlocfilehash: 1f85b1ce95ca07329aff77af4ec894622e0818d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606743"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="c3250-101">Los tipos de WorkFlow 3.0 están obsoletos</span><span class="sxs-lookup"><span data-stu-id="c3250-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="c3250-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c3250-102">Details</span></span>

<span data-ttu-id="c3250-103">Las API de Windows Workflow Foundation (WWF) 3.0 (las procedentes del espacio de nombres System.Workflow) ahora están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="c3250-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c3250-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c3250-104">Suggestion</span></span>

<span data-ttu-id="c3250-105">En su lugar, deben usarse nuevas API de WWF 4.0 (en System.Activities).</span><span class="sxs-lookup"><span data-stu-id="c3250-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="c3250-106">Puede encontrar un ejemplo de uso de las nuevas API [aquí](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md). Hay disponible más información [aquí](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span><span class="sxs-lookup"><span data-stu-id="c3250-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="c3250-107">Además, las API de WWF 3.0 continúan siendo compatibles, por lo que pueden seguir usándose. También se puede evitar la advertencia de tiempo de compilación suprimiéndola o usando un compilador anterior.</span><span class="sxs-lookup"><span data-stu-id="c3250-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="c3250-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c3250-108">Name</span></span>    | <span data-ttu-id="c3250-109">Valor</span><span class="sxs-lookup"><span data-stu-id="c3250-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c3250-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c3250-110">Scope</span></span>   | <span data-ttu-id="c3250-111">Major</span><span class="sxs-lookup"><span data-stu-id="c3250-111">Major</span></span>       |
| <span data-ttu-id="c3250-112">Versión</span><span class="sxs-lookup"><span data-stu-id="c3250-112">Version</span></span> | <span data-ttu-id="c3250-113">4.5</span><span class="sxs-lookup"><span data-stu-id="c3250-113">4.5</span></span>         |
| <span data-ttu-id="c3250-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c3250-114">Type</span></span>    | <span data-ttu-id="c3250-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="c3250-115">Retargeting</span></span> |
