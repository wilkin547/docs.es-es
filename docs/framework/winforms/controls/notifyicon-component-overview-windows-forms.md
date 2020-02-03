---
title: Información general sobre el componente NotifyIcon
ms.date: 03/30/2017
f1_keywords:
- NotifyIcon
helpviewer_keywords:
- NotifyIcon component [Windows Forms], about NotifyIcon component
- system tray icons [Windows Forms], about system tray icons
- system tray icons [Windows Forms], using in Windows Forms
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
ms.openlocfilehash: 587bf514db853f1122ed16abc05a195985c5ce8d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742124"
---
# <a name="notifyicon-component-overview-windows-forms"></a><span data-ttu-id="9a3aa-102">Información general sobre el componente NotifyIcon (Formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="9a3aa-102">NotifyIcon Component Overview (Windows Forms)</span></span>

<span data-ttu-id="9a3aa-103">El componente <xref:System.Windows.Forms.NotifyIcon> de Windows Forms se usa normalmente para mostrar iconos para los procesos que se ejecutan en segundo plano y no muestran una interfaz de usuario gran parte del tiempo.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component is typically used to display icons for processes that run in the background and do not show a user interface much of the time.</span></span> <span data-ttu-id="9a3aa-104">Un ejemplo sería un programa antivirus al que se puede acceder haciendo clic en un icono en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-104">An example would be a virus protection program that can be accessed by clicking an icon in the status notification area of the taskbar.</span></span>

## <a name="key-properties-of-notifyicons"></a><span data-ttu-id="9a3aa-105">Propiedades clave de NotifyIcons</span><span class="sxs-lookup"><span data-stu-id="9a3aa-105">Key Properties of NotifyIcons</span></span>

<span data-ttu-id="9a3aa-106">Cada componente <xref:System.Windows.Forms.NotifyIcon> muestra un solo icono en el área de estado.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-106">Each <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status area.</span></span> <span data-ttu-id="9a3aa-107">Si tiene tres procesos en segundo plano y quiere mostrar un icono para cada uno, deberá agregar tres componentes <xref:System.Windows.Forms.NotifyIcon> al formulario.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-107">If you have three background processes and wish to display an icon for each, you must add three <xref:System.Windows.Forms.NotifyIcon> components to the form.</span></span> <span data-ttu-id="9a3aa-108">Las propiedades clave del componente <xref:System.Windows.Forms.NotifyIcon> son <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-108">The key properties of the <xref:System.Windows.Forms.NotifyIcon> component are <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span></span> <span data-ttu-id="9a3aa-109">La propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> establece el icono que aparece en el área de estado.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-109">The <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property sets the icon that appears in the status area.</span></span> <span data-ttu-id="9a3aa-110">Para que el icono aparezca, la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> debe establecerse en `true`.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-110">In order for the icon to appear, the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property must be set to `true`.</span></span>

## <a name="notifyicons-options"></a><span data-ttu-id="9a3aa-111">Opciones de NotifyIcons</span><span class="sxs-lookup"><span data-stu-id="9a3aa-111">NotifyIcons Options</span></span>

<span data-ttu-id="9a3aa-112">Puede asociar globos de sugerencias, menús contextuales e información sobre herramientas a un <xref:System.Windows.Forms.NotifyIcon> para ayudar al usuario.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-112">You can associate balloon tips, shortcut menus, and ToolTips with a <xref:System.Windows.Forms.NotifyIcon> to assist the user.</span></span>

<span data-ttu-id="9a3aa-113">Para mostrar globos de sugerencias para un <xref:System.Windows.Forms.NotifyIcon>, llame al método <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> y especifique el intervalo de tiempo que quiere que el globo de sugerencias se muestre.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-113">You can display balloon tips for a <xref:System.Windows.Forms.NotifyIcon> by calling the <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> method specifying the time span you wish the balloon tip to display.</span></span> <span data-ttu-id="9a3aa-114">También puede especificar el texto, el icono y el título del globo de sugerencias con <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> y <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-114">You can also specify the text, icon and title of the balloon tip with the <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> and <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectively.</span></span> <span data-ttu-id="9a3aa-115">Los componentes <xref:System.Windows.Forms.NotifyIcon> también pueden tener asociada información sobre herramientas y menús contextuales.</span><span class="sxs-lookup"><span data-stu-id="9a3aa-115"><xref:System.Windows.Forms.NotifyIcon> components can also have associated ToolTips and shortcut menus.</span></span> <span data-ttu-id="9a3aa-116">Para obtener más información, vea información general sobre los [componentes ToolTip](tooltip-component-overview-windows-forms.md) e [información general sobre el componente ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9a3aa-116">For more information, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md) and [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9a3aa-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9a3aa-117">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- [<span data-ttu-id="9a3aa-118">NotifyIcon (componente)</span><span class="sxs-lookup"><span data-stu-id="9a3aa-118">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
