---
title: Sistemas de ayuda en aplicaciones de Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45d3385d008f823050f213252fdc2e1851cf422b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="f87bd-102">Sistemas de ayuda en aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f87bd-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="f87bd-103">Una de las ventajas más importantes, como un desarrollador de aplicaciones, puede ofrecer a los usuarios es un sistema de ayuda eficaz.</span><span class="sxs-lookup"><span data-stu-id="f87bd-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="f87bd-104">Esto es donde mostrará en color cuando estén confundidos o desorientados.</span><span class="sxs-lookup"><span data-stu-id="f87bd-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="f87bd-105">Proporcionar un sistema de ayuda en una aplicación basada en Windows se realiza fácilmente mediante la [HelpProvider (componente)](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f87bd-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="f87bd-106">Diferentes tipos de ayuda</span><span class="sxs-lookup"><span data-stu-id="f87bd-106">Different Types of Help</span></span>  
 <span data-ttu-id="f87bd-107">El componente <xref:System.Windows.Forms.HelpProvider> de Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x (ya sea un archivo .chm generado con HTML Help Workshop o un archivo .htm) con una aplicación basada en Windows.</span><span class="sxs-lookup"><span data-stu-id="f87bd-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="f87bd-108">El <xref:System.Windows.Forms.HelpProvider> componente puede utilizarse para proporcionar ayuda contextual para los controles en formularios Windows Forms o controles específicos.</span><span class="sxs-lookup"><span data-stu-id="f87bd-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="f87bd-109">Además, la <xref:System.Windows.Forms.HelpProvider> componente puede abrir un archivo de ayuda en áreas específicas, como la página principal de una tabla de contenido, un índice o una función de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f87bd-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="f87bd-110">Para obtener información general sobre la <xref:System.Windows.Forms.HelpProvider> componente, vea [general sobre el componente HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f87bd-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../../../../docs/framework/winforms/controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="f87bd-111">Para obtener información sobre cómo usar el <xref:System.Windows.Forms.HelpProvider> componente para mostrar Ayuda emergente en formularios Windows Forms, vea [Cómo: mostrar Ayuda emergente](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span><span class="sxs-lookup"><span data-stu-id="f87bd-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="f87bd-112">Para obtener información sobre el uso de la <xref:System.Windows.Forms.ToolTip> componente para mostrar ayuda específica del control, vea [Control ayuda mediante información sobre herramientas](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span><span class="sxs-lookup"><span data-stu-id="f87bd-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="f87bd-113">Puede generar archivos HTML Help 1.x con HTML Help Workshop.</span><span class="sxs-lookup"><span data-stu-id="f87bd-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="f87bd-114">Para obtener más información sobre la Ayuda HTML, vea "HTML Help Workshop" o los otros temas de "Ayuda HTML" en MSDN.</span><span class="sxs-lookup"><span data-stu-id="f87bd-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87bd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f87bd-115">See Also</span></span>  
 [<span data-ttu-id="f87bd-116">Integrar la Ayuda de usuario en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f87bd-116">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="f87bd-117">HelpProvider (componente)</span><span class="sxs-lookup"><span data-stu-id="f87bd-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 [<span data-ttu-id="f87bd-118">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="f87bd-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 [<span data-ttu-id="f87bd-119">Información general sobre formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f87bd-119">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 [<span data-ttu-id="f87bd-120">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f87bd-120">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
