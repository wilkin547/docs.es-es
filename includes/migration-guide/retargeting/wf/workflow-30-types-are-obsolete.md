---
ms.openlocfilehash: 358103d5816eb61c88738e9626fb02c563b507f8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617306"
---
### <a name="workflow-30-types-are-obsolete"></a><span data-ttu-id="f5123-101">Los tipos de WorkFlow 3.0 están obsoletos</span><span class="sxs-lookup"><span data-stu-id="f5123-101">WorkFlow 3.0 types are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="f5123-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f5123-102">Details</span></span>

<span data-ttu-id="f5123-103">Las API de Windows Workflow Foundation (WWF) 3.0 (las procedentes del espacio de nombres System.Workflow) ahora están obsoletas.</span><span class="sxs-lookup"><span data-stu-id="f5123-103">Windows Workflow Foundation (WWF) 3.0 APIs (those from the System.Workflow namespace) are now obsolete.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f5123-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f5123-104">Suggestion</span></span>

<span data-ttu-id="f5123-105">En su lugar, deben usarse nuevas API de WWF 4.0 (en System.Activities).</span><span class="sxs-lookup"><span data-stu-id="f5123-105">New WWF 4.0 APIs (in System.Activities) should be used instead.</span></span> <span data-ttu-id="f5123-106">Puede encontrar un ejemplo de uso de las nuevas API [aquí](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md). Hay disponible más información [aquí](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span><span class="sxs-lookup"><span data-stu-id="f5123-106">An example of using the new APIs can be found [here](~/docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md) and further guidance is available [here](https://docs.microsoft.com/archive/blogs/workflowteam/wf3-types-marked-obsolete-in-net-4-5).</span></span> <span data-ttu-id="f5123-107">Además, las API de WWF 3.0 continúan siendo compatibles, por lo que pueden seguir usándose. También se puede evitar la advertencia de tiempo de compilación suprimiéndola o usando un compilador anterior.</span><span class="sxs-lookup"><span data-stu-id="f5123-107">Alternatively, since the WWF 3.0 APIs are still supported, they may be used and the build-time warning avoided either by suppressing it or by using an older compiler.</span></span>

| <span data-ttu-id="f5123-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="f5123-108">Name</span></span>    | <span data-ttu-id="f5123-109">Valor</span><span class="sxs-lookup"><span data-stu-id="f5123-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f5123-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f5123-110">Scope</span></span>   | <span data-ttu-id="f5123-111">Major</span><span class="sxs-lookup"><span data-stu-id="f5123-111">Major</span></span>       |
| <span data-ttu-id="f5123-112">Versión</span><span class="sxs-lookup"><span data-stu-id="f5123-112">Version</span></span> | <span data-ttu-id="f5123-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f5123-113">4.5</span></span>         |
| <span data-ttu-id="f5123-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="f5123-114">Type</span></span>    | <span data-ttu-id="f5123-115">Redestinación</span><span class="sxs-lookup"><span data-stu-id="f5123-115">Retargeting</span></span> |
