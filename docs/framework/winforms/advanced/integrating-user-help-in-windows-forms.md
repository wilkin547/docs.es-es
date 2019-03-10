---
title: Integrar la Ayuda de usuario en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715313"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="628f0-102">Integrar la Ayuda de usuario en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="628f0-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="628f0-103">Un aspecto esencial de la creación de aplicaciones basadas en Windows, que a menudo se pasa por alto, es el sistema de ayuda, ya que esto es donde los usuarios activar para obtener ayuda en momentos de confusión.</span><span class="sxs-lookup"><span data-stu-id="628f0-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="628f0-104">Windows Forms admiten dos tipos diferentes de la Ayuda, cada una proporcionada por el [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="628f0-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="628f0-105">La primera implica sugerir al usuario a un archivo de Ayuda de HTML o HTML Help 1. *x* o superior.</span><span class="sxs-lookup"><span data-stu-id="628f0-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="628f0-106">El segundo puede mostrar breve "¿Qué es esto"-escriba Help en controles individuales; Esto es especialmente útil en los cuadros de diálogo.</span><span class="sxs-lookup"><span data-stu-id="628f0-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="628f0-107">Ambos tipos de ayuda pueden usarse en el mismo formulario.</span><span class="sxs-lookup"><span data-stu-id="628f0-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="628f0-108">Además, el [componente ToolTip](../controls/tooltip-component-windows-forms.md) puede usarse para proporcionar ayuda individual para controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="628f0-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="628f0-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="628f0-109">In This Section</span></span>  
 [<span data-ttu-id="628f0-110">Cómo: Proporcionar ayuda en una aplicación de Windows</span><span class="sxs-lookup"><span data-stu-id="628f0-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="628f0-111">Explica cómo utilizar el `HelpProvider` componente para vincular controles a archivos en un sistema de ayuda.</span><span class="sxs-lookup"><span data-stu-id="628f0-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="628f0-112">Cómo: Mostrar ayuda emergente</span><span class="sxs-lookup"><span data-stu-id="628f0-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="628f0-113">Explica cómo utilizar el `HelpProvider` componente para mostrar Ayuda emergente en los formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="628f0-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="628f0-114">Controlar la ayuda mediante componentes Tooltip</span><span class="sxs-lookup"><span data-stu-id="628f0-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="628f0-115">Describe cómo utilizar el `ToolTip` componente para mostrar la ayuda específica del control.</span><span class="sxs-lookup"><span data-stu-id="628f0-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="628f0-116">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="628f0-116">Related Sections</span></span>  
 [<span data-ttu-id="628f0-117">HelpProvider (componente)</span><span class="sxs-lookup"><span data-stu-id="628f0-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="628f0-118">Explica los conceptos básicos de la `HelpProvider` componente.</span><span class="sxs-lookup"><span data-stu-id="628f0-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="628f0-119">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="628f0-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="628f0-120">Explica los conceptos básicos de la `ToolTip` componente.</span><span class="sxs-lookup"><span data-stu-id="628f0-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="628f0-121">Información general sobre formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="628f0-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="628f0-122">Explica los conceptos básicos de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="628f0-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="628f0-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="628f0-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="628f0-124">Proporciona información general de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="628f0-124">Provides an overview of Windows Forms.</span></span>
