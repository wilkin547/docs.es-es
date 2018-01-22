---
title: "Cómo: Heredar de una clase UserControl"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- UserControl class [Windows Forms], inheriting from
- user controls [Windows Forms], creating
- composite controls [Windows Forms], creating
ms.assetid: 67713625-e2e4-4f6a-bce7-0855ee5043d9
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5eec04e6122f32321c34efe030bfca943baed5bf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-inherit-from-the-usercontrol-class"></a><span data-ttu-id="687ab-102">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="687ab-102">How to: Inherit from the UserControl Class</span></span>
<span data-ttu-id="687ab-103">Para combinar la funcionalidad de uno o más controles de Windows Forms con código personalizado, puede crear un *control de usuario*.</span><span class="sxs-lookup"><span data-stu-id="687ab-103">To combine the functionality of one or more Windows Forms controls with custom code, you can create a *user control*.</span></span> <span data-ttu-id="687ab-104">Los controles de usuario combinan el desarrollo rápido de controles, la funcionalidad de los controles de Windows Forms estándar y la versatilidad de los métodos y las propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="687ab-104">User controls combine rapid control development, standard Windows Forms control functionality, and the versatility of custom properties and methods.</span></span> <span data-ttu-id="687ab-105">Al comenzar a crear un control de usuario, se le presentará un diseñador visible en el que puede colocar los controles de Windows Forms estándar.</span><span class="sxs-lookup"><span data-stu-id="687ab-105">When you begin creating a user control, you are presented with a visible designer, upon which you can place standard Windows Forms controls.</span></span> <span data-ttu-id="687ab-106">Estos controles conservan toda su funcionalidad inherente, así como la apariencia y el comportamiento (apariencia) de los controles estándar.</span><span class="sxs-lookup"><span data-stu-id="687ab-106">These controls retain all of their inherent functionality, as well as the appearance and behavior (look and feel) of standard controls.</span></span> <span data-ttu-id="687ab-107">Una vez que estos controles están integrados en el control de usuario, dejan de estar disponibles en el código.</span><span class="sxs-lookup"><span data-stu-id="687ab-107">Once these controls are built into the user control, however, they are no longer available to you through code.</span></span> <span data-ttu-id="687ab-108">El control de usuario realiza su propio dibujo y controla también toda la funcionalidad básica asociada a los controles.</span><span class="sxs-lookup"><span data-stu-id="687ab-108">The user control does its own painting and also handles all of the basic functionality associated with controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="687ab-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="687ab-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="687ab-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="687ab-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="687ab-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="687ab-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-user-control"></a><span data-ttu-id="687ab-112">Crear un control de usuario</span><span class="sxs-lookup"><span data-stu-id="687ab-112">To create a user control</span></span>  
  
1.  <span data-ttu-id="687ab-113">Cree un nuevo proyecto de tipo **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="687ab-113">Create a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="687ab-114">Se crea un nuevo proyecto con un control de usuario en blanco.</span><span class="sxs-lookup"><span data-stu-id="687ab-114">A new project is created with a blank user control.</span></span>  
  
2.  <span data-ttu-id="687ab-115">Arrastre controles desde la pestaña **Windows Forms** de **Cuadro de herramientas** en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="687ab-115">Drag controls from the **Windows Forms** tab of the **Toolbox** onto your designer.</span></span>  
  
3.  <span data-ttu-id="687ab-116">Estos controles deben estar situados y diseñados como desee que aparezcan en el control de usuario final.</span><span class="sxs-lookup"><span data-stu-id="687ab-116">These controls should be positioned and designed as you want them to appear in the final user control.</span></span> <span data-ttu-id="687ab-117">Si desea permitir a los desarrolladores tener acceso a los controles constituyentes, deberá declararlos públicos o exponer de forma selectiva las propiedades del control constituyente.</span><span class="sxs-lookup"><span data-stu-id="687ab-117">If you want to allow developers to access the constituent controls, you must declare them as public, or selectively expose properties of the constituent control.</span></span> <span data-ttu-id="687ab-118">Para obtener detalles, vea [Cómo: Exponer propiedades de controles constituyentes](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span><span class="sxs-lookup"><span data-stu-id="687ab-118">For details, see [How to: Expose Properties of Constituent Controls](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md).</span></span>  
  
4.  <span data-ttu-id="687ab-119">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="687ab-119">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
5.  <span data-ttu-id="687ab-120">Presione F5 para compilar el proyecto y ejecutar el control en **UserControl Test Container**.</span><span class="sxs-lookup"><span data-stu-id="687ab-120">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="687ab-121">Para más información, consulte [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="687ab-121">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="687ab-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="687ab-122">See Also</span></span>  
 [<span data-ttu-id="687ab-123">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="687ab-123">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="687ab-124">Cómo: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="687ab-124">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="687ab-125">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="687ab-125">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="687ab-126">Cómo: Crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="687ab-126">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="687ab-127">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="687ab-127">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="687ab-128">Cómo: Comprobar el comportamiento de una clase UserControl en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="687ab-128">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)
