---
title: Procedimiento para bloquear controles en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f6dd079331c6c1883839efe5c6cb127044380fd2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987470"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="1c9d3-102">Procedimiento Bloquear controles en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c9d3-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="1c9d3-103">Al diseñar la interfaz de usuario (UI) de la aplicación Windows, puede bloquear los controles una vez que se colocan correctamente, de modo que no los mueva o cambie de tamaño accidentalmente al establecer otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="1c9d3-104">Además, puede bloquear y desbloquear todos los controles del formulario a la vez, lo que resulta útil para los formularios con muchos controles o puede desbloquear controles individuales.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="1c9d3-105">Una vez que haya colocado todos los controles que desee en el formulario, bloquee todos en su lugar para evitar un movimiento erróneo.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="1c9d3-106">Para bloquear un control</span><span class="sxs-lookup"><span data-stu-id="1c9d3-106">To lock a control</span></span>

<span data-ttu-id="1c9d3-107">En la ventana **propiedades** de Visual Studio, seleccione la propiedad **bloqueado** y, a continuación, seleccione **true**.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="1c9d3-108">(Si hace doble clic en el nombre, se alterna el valor de la propiedad).</span><span class="sxs-lookup"><span data-stu-id="1c9d3-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="1c9d3-109">También puede hacer clic con el botón secundario en el control y elegir **bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="1c9d3-110">Los controles de bloqueo evitan que se arrastren a un nuevo tamaño o ubicación en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="1c9d3-111">Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles mediante la ventana **propiedades** o en el código.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="1c9d3-112">Para bloquear todos los controles de un formulario</span><span class="sxs-lookup"><span data-stu-id="1c9d3-112">To lock all the controls on a form</span></span>

<span data-ttu-id="1c9d3-113">En el menú **formato** , elija **bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="1c9d3-114">Este comando bloquea también el tamaño del formulario, porque un formulario es un control.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="1c9d3-115">Para desbloquear todos los controles bloqueados en un formulario</span><span class="sxs-lookup"><span data-stu-id="1c9d3-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="1c9d3-116">En el menú **formato** , elija **bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="1c9d3-117">Todos los controles previamente bloqueados en el formulario están ahora desbloqueados.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="1c9d3-118">Para desbloquear controles bloqueados individualmente</span><span class="sxs-lookup"><span data-stu-id="1c9d3-118">To unlock locked controls individually</span></span>

<span data-ttu-id="1c9d3-119">En la ventana **propiedades** , seleccione la propiedad **bloqueado** y, a continuación, seleccione **false**.</span><span class="sxs-lookup"><span data-stu-id="1c9d3-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="1c9d3-120">(Si hace doble clic en el nombre, se alterna el valor de la propiedad).</span><span class="sxs-lookup"><span data-stu-id="1c9d3-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="1c9d3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c9d3-121">See also</span></span>

- [<span data-ttu-id="1c9d3-122">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c9d3-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="1c9d3-123">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="1c9d3-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="1c9d3-124">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1c9d3-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="1c9d3-125">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="1c9d3-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
