---
description: Más información sobre cómo personalizar la experiencia de diseño de flujo de trabajo
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 02049f8b42de3de6e4dfdfe8a4151be1500bcca9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742659"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="c8330-103">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c8330-103">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="c8330-104">Los escenarios para diseñar actividades personalizadas y para rehospedar el Diseñador de flujo de trabajo de Windows se han simplificado en gran medida en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c8330-104">The scenarios for designing custom activities and for rehosting the Windows Workflow Designer have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="c8330-105">El desarrollo y la implementación resultan ahora más fáciles y más flexibles.</span><span class="sxs-lookup"><span data-stu-id="c8330-105">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="c8330-106">El cambio de clave infraestructura es que el nuevo modelo de programación del diseñador de actividad se basa en Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c8330-106">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c8330-107">Esto le ofrece la posibilidad de definir diseñadores de actividad de forma declarativa y de rehospedar el Diseñador de flujo de trabajo en otras aplicaciones con facilidad comparativa.</span><span class="sxs-lookup"><span data-stu-id="c8330-107">This gives you the ability to define activity designers declaratively and to rehost the Workflow Designer in other applications with comparative easy.</span></span> <span data-ttu-id="c8330-108">Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado.</span><span class="sxs-lookup"><span data-stu-id="c8330-108">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="c8330-109">La integración con Windows Communication Foundation (WCF) ha vuelto a ser más fluida con el uso de los servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c8330-109">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="c8330-110">Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.</span><span class="sxs-lookup"><span data-stu-id="c8330-110">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c8330-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c8330-111">In This Section</span></span>

 [<span data-ttu-id="c8330-112">Usar plantillas y diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="c8330-112">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="c8330-113">Describe cómo crear diseñadores de actividad personalizados y plantillas.</span><span class="sxs-lookup"><span data-stu-id="c8330-113">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="c8330-114">Rehospedar el Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c8330-114">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="c8330-115">Describe cómo volver a hospedar el Diseñador de flujo de trabajo de Windows fuera de Visual Studio y cómo mostrar los errores de validación.</span><span class="sxs-lookup"><span data-stu-id="c8330-115">Describes how to re-host the Windows Workflow Designer outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="c8330-116">Usar un editor de expresiones personalizado</span><span class="sxs-lookup"><span data-stu-id="c8330-116">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="c8330-117">Describe cómo implementar un editor de expresiones personalizado para usarlo con diseñadores de flujo de trabajo rehospedados fuera de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="c8330-117">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="c8330-118">Referencia</span><span class="sxs-lookup"><span data-stu-id="c8330-118">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="c8330-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8330-119">See also</span></span>

- [<span data-ttu-id="c8330-120">Ampliar Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="c8330-120">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="c8330-121">Designer</span><span class="sxs-lookup"><span data-stu-id="c8330-121">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="c8330-122">Diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="c8330-122">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="c8330-123">Rehost del diseñador</span><span class="sxs-lookup"><span data-stu-id="c8330-123">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
