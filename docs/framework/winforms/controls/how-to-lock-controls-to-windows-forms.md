---
title: Filtrar para bloquear controles en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: ac5fbf33564ed2dd1a030132a35b36164f777519
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301703"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="433a4-102">Filtrar para bloquear controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="433a4-102">How to: Lock Controls to Windows Forms</span></span>
<span data-ttu-id="433a4-103">Al diseñar la interfaz de usuario (UI) de la aplicación de Windows, puede bloquear los controles una vez que se colocan correctamente, por lo que no accidentalmente mover o cambiar su tamaño al establecer otras propiedades.</span><span class="sxs-lookup"><span data-stu-id="433a4-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>  
  
 <span data-ttu-id="433a4-104">Además, puede bloquear y desbloquear todos los controles del formulario a la vez, lo cual resulta útil para formularios con muchos controles, o puede desbloquear controles individuales.</span><span class="sxs-lookup"><span data-stu-id="433a4-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="433a4-105">Una vez que haya colocado todos los controles donde desee en el formulario, bloquear en lugar de para evitar movimientos erróneos.</span><span class="sxs-lookup"><span data-stu-id="433a4-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="433a4-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="433a4-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="433a4-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="433a4-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="433a4-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="433a4-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-lock-a-control"></a><span data-ttu-id="433a4-109">Para bloquear un control</span><span class="sxs-lookup"><span data-stu-id="433a4-109">To lock a control</span></span>  
  
1. <span data-ttu-id="433a4-110">En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `true`.</span><span class="sxs-lookup"><span data-stu-id="433a4-110">In the **Properties** window, click the **Locked** property and select `true`.</span></span> <span data-ttu-id="433a4-111">(Haga doble clic en el nombre, se alterna el valor de propiedad).</span><span class="sxs-lookup"><span data-stu-id="433a4-111">(Double-clicking the name toggles the property setting.)</span></span>  
  
     <span data-ttu-id="433a4-112">Como alternativa, haga clic en el control y elija **Bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="433a4-112">Alternatively, right-click the control and choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="433a4-113">Controles de bloqueo impide que se arrastran a un nuevo tamaño o la ubicación en la superficie de diseño.</span><span class="sxs-lookup"><span data-stu-id="433a4-113">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="433a4-114">Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles por medio de la **propiedades** ventana o en el código.</span><span class="sxs-lookup"><span data-stu-id="433a4-114">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>  
  
### <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="433a4-115">Para bloquear todos los controles en un formulario</span><span class="sxs-lookup"><span data-stu-id="433a4-115">To lock all the controls on a form</span></span>  
  
1. <span data-ttu-id="433a4-116">Desde el **formato** menú, elija **Bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="433a4-116">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="433a4-117">Este comando bloquea el tamaño del formulario, como el formulario es un control.</span><span class="sxs-lookup"><span data-stu-id="433a4-117">This command locks the form's size as well, because a form is a control.</span></span>  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="433a4-118">Para desbloquear todos los controles en un formulario bloqueados</span><span class="sxs-lookup"><span data-stu-id="433a4-118">To unlock all locked controls on a form</span></span>  
  
1. <span data-ttu-id="433a4-119">Desde el **formato** menú, elija **Bloquear controles**.</span><span class="sxs-lookup"><span data-stu-id="433a4-119">From the **Format** menu, choose **Lock Controls**.</span></span>  
  
     <span data-ttu-id="433a4-120">Todos los controles del formulario estaba bloqueados ahora están desbloqueada.</span><span class="sxs-lookup"><span data-stu-id="433a4-120">All previously locked controls on the form are now unlocked.</span></span>  
  
### <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="433a4-121">Para desbloquear individualmente los controles bloqueados</span><span class="sxs-lookup"><span data-stu-id="433a4-121">To unlock locked controls individually</span></span>  
  
1. <span data-ttu-id="433a4-122">En el **propiedades** ventana, haga clic en el **bloqueado** propiedad y seleccione `false`.</span><span class="sxs-lookup"><span data-stu-id="433a4-122">In the **Properties** window, click the **Locked** property and select `false`.</span></span> <span data-ttu-id="433a4-123">(Haga doble clic en el nombre, se alterna el valor de propiedad).</span><span class="sxs-lookup"><span data-stu-id="433a4-123">(Double-clicking the name toggles the property setting.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="433a4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="433a4-124">See also</span></span>

- [<span data-ttu-id="433a4-125">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="433a4-125">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="433a4-126">Organizar controles en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="433a4-126">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="433a4-127">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="433a4-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="433a4-128">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="433a4-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="433a4-129">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="433a4-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
