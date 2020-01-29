---
title: Integración de la ayuda del usuario
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: c402615d68c75327613d21bd35f1587b10f1dbf3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731566"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="88193-102">Integrar la Ayuda de usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88193-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="88193-103">Un aspecto esencial, que a menudo se pasa por alto, de la creación de aplicaciones basadas en Windows es el sistema de ayuda, ya que aquí es donde los usuarios activan la asistencia en momentos de confusión.</span><span class="sxs-lookup"><span data-stu-id="88193-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="88193-104">Windows Forms admiten dos tipos diferentes de ayuda, cada uno proporcionado por el [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="88193-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="88193-105">El primero implica apuntar al usuario a un archivo de ayuda de HTML o HTML Help 1. formato *x* o superior.</span><span class="sxs-lookup"><span data-stu-id="88193-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="88193-106">El segundo puede mostrar brevemente la ayuda de tipo "What is this" (Qué es esto) en controles individuales; Esto es especialmente útil en los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="88193-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="88193-107">Ambos tipos de ayuda se pueden usar en el mismo formulario.</span><span class="sxs-lookup"><span data-stu-id="88193-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="88193-108">Además, el [componente ToolTip](../controls/tooltip-component-windows-forms.md) se puede usar para proporcionar ayuda individual para los controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88193-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88193-109">Esta sección</span><span class="sxs-lookup"><span data-stu-id="88193-109">In This Section</span></span>  
 [<span data-ttu-id="88193-110">Proporcionar ayuda en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="88193-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="88193-111">Explica cómo utilizar el componente `HelpProvider` para vincular controles a archivos en un sistema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="88193-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="88193-112">Mostrar ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="88193-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="88193-113">Explica cómo usar el componente `HelpProvider` para mostrar ayuda emergente sobre Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88193-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="88193-114">Controlar la ayuda mediante componentes Tooltip</span><span class="sxs-lookup"><span data-stu-id="88193-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="88193-115">Describe el uso del componente `ToolTip` para mostrar la ayuda específica del control.</span><span class="sxs-lookup"><span data-stu-id="88193-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="88193-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="88193-116">Related Sections</span></span>  
 [<span data-ttu-id="88193-117">HelpProvider (componente)</span><span class="sxs-lookup"><span data-stu-id="88193-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="88193-118">Explica los aspectos básicos del componente `HelpProvider`.</span><span class="sxs-lookup"><span data-stu-id="88193-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="88193-119">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="88193-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="88193-120">Explica los aspectos básicos del componente `ToolTip`.</span><span class="sxs-lookup"><span data-stu-id="88193-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="88193-121">Información general sobre formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88193-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="88193-122">Explica los aspectos básicos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88193-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="88193-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88193-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="88193-124">Proporciona información general sobre Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="88193-124">Provides an overview of Windows Forms.</span></span>
