---
title: Integrar la Ayuda de usuario en formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7ec4d32c5f025cb3e48b1403387273268d83fb8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="049f0-102">Integrar la Ayuda de usuario en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="049f0-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="049f0-103">Un aspecto fundamental, pero a menudo se pasa por alto, de la creación de aplicaciones basadas en Windows es el sistema de ayuda, puesto que éste es donde los usuarios activan para obtener ayuda en momentos de confusión.</span><span class="sxs-lookup"><span data-stu-id="049f0-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="049f0-104">Formularios Windows Forms admiten dos tipos diferentes de la Ayuda, cada proporcionado por el [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="049f0-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="049f0-105">El primero implica indicar al usuario a un archivo de Ayuda de HTML o HTML Help 1. *x* o formato mayor.</span><span class="sxs-lookup"><span data-stu-id="049f0-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="049f0-106">El segundo puede mostrar breve "¿Qué es esto"-escriba Help en controles individuales; Esto es especialmente útil en los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="049f0-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="049f0-107">Ambos tipos de ayuda pueden usarse en el mismo formulario.</span><span class="sxs-lookup"><span data-stu-id="049f0-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="049f0-108">Además, el [ToolTip (componente)](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) puede utilizarse para proporcionar ayuda individual para los controles de formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="049f0-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="049f0-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="049f0-109">In This Section</span></span>  
 [<span data-ttu-id="049f0-110">Proporcionar ayuda en una aplicación para Windows</span><span class="sxs-lookup"><span data-stu-id="049f0-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="049f0-111">Explica cómo utilizar el `HelpProvider` componente para vincular controles a archivos en un sistema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="049f0-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="049f0-112">Mostrar ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="049f0-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="049f0-113">Explica cómo utilizar el `HelpProvider` componente para mostrar Ayuda emergente en formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="049f0-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="049f0-114">Controlar la ayuda mediante componentes Tooltip</span><span class="sxs-lookup"><span data-stu-id="049f0-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="049f0-115">Describe cómo utilizar el `ToolTip` componente para mostrar la ayuda específica del control.</span><span class="sxs-lookup"><span data-stu-id="049f0-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="049f0-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="049f0-116">Related Sections</span></span>  
 [<span data-ttu-id="049f0-117">HelpProvider (componente)</span><span class="sxs-lookup"><span data-stu-id="049f0-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="049f0-118">Explica los fundamentos de la `HelpProvider` componente.</span><span class="sxs-lookup"><span data-stu-id="049f0-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="049f0-119">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="049f0-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="049f0-120">Explica los fundamentos de la `ToolTip` componente.</span><span class="sxs-lookup"><span data-stu-id="049f0-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="049f0-121">Información general sobre formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="049f0-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="049f0-122">Explica los fundamentos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="049f0-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="049f0-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="049f0-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="049f0-124">Proporciona información general sobre formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="049f0-124">Provides an overview of Windows Forms.</span></span>
