---
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 926edb4478551affa03619f44ee886d5eb591e4d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637274"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="015d8-102">Personalizar la experiencia de diseño del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="015d8-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="015d8-103">Los escenarios para diseñar las actividades personalizadas y para re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] se han simplificado enormemente en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="015d8-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="015d8-104">El desarrollo y la implementación resultan ahora más fáciles y más flexibles.</span><span class="sxs-lookup"><span data-stu-id="015d8-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="015d8-105">El cambio infraestructural clave es que el nuevo modelo de programación Diseñador de actividad se basa en Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="015d8-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="015d8-106">Esto proporciona la capacidad de definir diseñadores de actividad mediante declaración y re-hospedar [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en otras aplicaciones con relativa facilidad.</span><span class="sxs-lookup"><span data-stu-id="015d8-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="015d8-107">Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado.</span><span class="sxs-lookup"><span data-stu-id="015d8-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="015d8-108">La integración con Windows Communication Foundation (WCF) se ha vuelto más uniforme con el uso de servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="015d8-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="015d8-109">Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.</span><span class="sxs-lookup"><span data-stu-id="015d8-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="015d8-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="015d8-110">In This Section</span></span>

 [<span data-ttu-id="015d8-111">Uso de plantillas y diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="015d8-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="015d8-112">Describe cómo crear diseñadores de actividad personalizados y plantillas.</span><span class="sxs-lookup"><span data-stu-id="015d8-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="015d8-113">Rehospedaje del Diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="015d8-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="015d8-114">Describe cómo volver a hospedar el [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] fuera de Visual Studio y cómo mostrar errores de validación.</span><span class="sxs-lookup"><span data-stu-id="015d8-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="015d8-115">Utilización de un editor de expresiones personalizado</span><span class="sxs-lookup"><span data-stu-id="015d8-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="015d8-116">Describe cómo implementar un editor de expresiones personalizado para usar con los diseñadores de flujo de trabajo rehospedados fuera de Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="015d8-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="015d8-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="015d8-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="015d8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="015d8-118">See also</span></span>

- [<span data-ttu-id="015d8-119">Extensión de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="015d8-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="015d8-120">Diseñador</span><span class="sxs-lookup"><span data-stu-id="015d8-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="015d8-121">Diseñadores de actividad personalizados</span><span class="sxs-lookup"><span data-stu-id="015d8-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="015d8-122">Rehospedaje del diseñador</span><span class="sxs-lookup"><span data-stu-id="015d8-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
