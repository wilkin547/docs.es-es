---
title: Procedimiento para heredar de la clase UserControl
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
ms.openlocfilehash: 77233517203989f188a2b3ddf436656bc8da82a6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966563"
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="73766-102">Procedimiento para heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="73766-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="73766-103">Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="73766-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="73766-104">Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="73766-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="73766-105">Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="73766-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="73766-106">Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar.</span><span class="sxs-lookup"><span data-stu-id="73766-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="73766-107">Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código.</span><span class="sxs-lookup"><span data-stu-id="73766-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="73766-108">El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.</span><span class="sxs-lookup"><span data-stu-id="73766-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>

## <a name="to-create-a-user-control"></a><span data-ttu-id="73766-109">Crear un control de usuario</span><span class="sxs-lookup"><span data-stu-id="73766-109">To create a user control</span></span>

1. <span data-ttu-id="73766-110">Cree un nuevo proyecto de tipo **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="73766-110">Create a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="73766-111">Se crea un nuevo proyecto con un control de usuario en blanco.</span><span class="sxs-lookup"><span data-stu-id="73766-111">A new project is created with a blank user control.</span></span>

2. <span data-ttu-id="73766-112">Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="73766-112">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>

3. <span data-ttu-id="73766-113">Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final.</span><span class="sxs-lookup"><span data-stu-id="73766-113">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="73766-114">Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="73766-114">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="73766-115">Para obtener más detalles, vea [Cómo: Exponga las propiedades de los](how-to-expose-properties-of-constituent-controls.md)controles constituyentes.</span><span class="sxs-lookup"><span data-stu-id="73766-115">For details, see [How to: Expose Properties of Constituent Controls](how-to-expose-properties-of-constituent-controls.md).</span></span>

4. <span data-ttu-id="73766-116">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="73766-116">Implement any custom methods or properties that your control will incorporate.</span></span>

5. <span data-ttu-id="73766-117">Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="73766-117">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="73766-118">Para obtener más información, vea [Cómo: Pruebe el comportamiento en tiempo de ejecución de un](how-to-test-the-run-time-behavior-of-a-usercontrol.md)control UserControl.</span><span class="sxs-lookup"><span data-stu-id="73766-118">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="73766-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="73766-119">See also</span></span>

- [<span data-ttu-id="73766-120">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="73766-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="73766-121">Cómo: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="73766-121">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="73766-122">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="73766-122">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="73766-123">Procedimientos: Controles de autor para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73766-123">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="73766-124">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73766-124">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="73766-125">Cómo: Probar el comportamiento en tiempo de ejecución de un control UserControl</span><span class="sxs-lookup"><span data-stu-id="73766-125">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
