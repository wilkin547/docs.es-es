---
title: "Información general sobre el componente NotifyIcon (Formularios Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8c909537bd4c52a546faeb83c6e9291c4de76d76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="d0089-102">Información general sobre el componente NotifyIcon (Formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="d0089-102">NotifyIcon Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d0089-103">El componente <xref:System.Windows.Forms.NotifyIcon> de Windows Forms se usa normalmente para mostrar iconos para los procesos que se ejecutan en segundo plano y no muestran una interfaz de usuario gran parte del tiempo.</span><span class="sxs-lookup"><span data-stu-id="d0089-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="d0089-104">Un ejemplo sería un programa antivirus al que se puede acceder haciendo clic en un icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="d0089-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>  
  
## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="d0089-105">Propiedades clave de NotifyIcons</span><span class="sxs-lookup"><span data-stu-id="d0089-105">Key Properties of NotifyIcons</span></span>  
 <span data-ttu-id="d0089-106">Cada componente <xref:System.Windows.Forms.NotifyIcon> muestra un solo icono en el área de estado.</span><span class="sxs-lookup"><span data-stu-id="d0089-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="d0089-107">Si tiene tres procesos en segundo plano y quiere mostrar un icono para cada uno, deberá agregar tres componentes <xref:System.Windows.Forms.NotifyIcon> al formulario.</span><span class="sxs-lookup"><span data-stu-id="d0089-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="d0089-108">Las propiedades clave del componente <xref:System.Windows.Forms.NotifyIcon> son <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="d0089-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="d0089-109">La propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> establece el icono que aparece en el área de estado.</span><span class="sxs-lookup"><span data-stu-id="d0089-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="d0089-110">Para que el icono aparezca, la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> debe establecerse en `true`.</span><span class="sxs-lookup"><span data-stu-id="d0089-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>  
  
 <span data-ttu-id="d0089-111">Si usa [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el control <xref:System.Windows.Forms.NotifyIcon>.</span><span class="sxs-lookup"><span data-stu-id="d0089-111">If you are using [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you have access to a large library of standard images that you can use with the <xref:System.Windows.Forms.NotifyIcon> control.</span></span>  
  
## <a name="notifyicons-options"></a><span data-ttu-id="d0089-112">Opciones de NotifyIcons</span><span class="sxs-lookup"><span data-stu-id="d0089-112">NotifyIcons Options</span></span>  
 <span data-ttu-id="d0089-113">Puede asociar globos de sugerencias, menús contextuales e información sobre herramientas a un <xref:System.Windows.Forms.NotifyIcon> para ayudar al usuario.</span><span class="sxs-lookup"><span data-stu-id="d0089-113">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>  
  
 <span data-ttu-id="d0089-114">Para mostrar globos de sugerencias para un <xref:System.Windows.Forms.NotifyIcon>, llame al método <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> y especifique el intervalo de tiempo que quiere que el globo de sugerencias se muestre.</span><span class="sxs-lookup"><span data-stu-id="d0089-114">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="d0089-115">También puede especificar el texto, el icono y el título del globo de sugerencias con <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> y <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d0089-115">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="d0089-116">Los componentes <xref:System.Windows.Forms.NotifyIcon> también pueden tener asociada información sobre herramientas y menús contextuales.</span><span class="sxs-lookup"><span data-stu-id="d0089-116"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="d0089-117">Para obtener más información, consulte [información general del componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) y [información general del componente ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d0089-117">For more information, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0089-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0089-118">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 [<span data-ttu-id="d0089-119">NotifyIcon (componente)</span><span class="sxs-lookup"><span data-stu-id="d0089-119">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
