---
title: Procedimiento para heredar de la clase Control
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02c40e310778bd476742f62ee8b9d8598b084a53
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015854"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="d9367-102">Procedimiento para heredar de la clase Control</span><span class="sxs-lookup"><span data-stu-id="d9367-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="d9367-103">Si desea crear un control completamente personalizado para usarlo en Windows Forms, debe heredar de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="d9367-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="d9367-104">Aunque la herencia de la <xref:System.Windows.Forms.Control> clase requiere que realice más planeación e implementación, también proporciona el mayor número de opciones.</span><span class="sxs-lookup"><span data-stu-id="d9367-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="d9367-105">Al heredar de <xref:System.Windows.Forms.Control>, se hereda la funcionalidad muy básica que hace que los controles funcionen.</span><span class="sxs-lookup"><span data-stu-id="d9367-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="d9367-106">La funcionalidad inherente en la <xref:System.Windows.Forms.Control> clase controla los datos proporcionados por el usuario a través del teclado y el mouse, define los límites y el tamaño del control, proporciona un identificador de Windows y proporciona seguridad y control de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d9367-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="d9367-107">No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico.</span><span class="sxs-lookup"><span data-stu-id="d9367-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="d9367-108">Debe proporcionar todos estos elementos por medio del código personalizado.</span><span class="sxs-lookup"><span data-stu-id="d9367-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="d9367-109">Para crear un color personalizado</span><span class="sxs-lookup"><span data-stu-id="d9367-109">To create a custom control</span></span>

1. <span data-ttu-id="d9367-110">En Visual Studio, cree una nueva **aplicación de Windows** o un proyecto de **biblioteca de controles de Windows** .</span><span class="sxs-lookup"><span data-stu-id="d9367-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="d9367-111">En el menú **Proyecto**, elija **Agregar clase**.</span><span class="sxs-lookup"><span data-stu-id="d9367-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="d9367-112">En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="d9367-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="d9367-113">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="d9367-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="d9367-114">Presione **F7** para abrir el **Editor de código** para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="d9367-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="d9367-115">Busque el <xref:System.Windows.Forms.Control.OnPaint%2A> método, que estará vacío excepto para una llamada <xref:System.Windows.Forms.Control.OnPaint%2A> al método de la clase base.</span><span class="sxs-lookup"><span data-stu-id="d9367-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="d9367-116">Modifique el código para incorporar el dibujo personalizado que desee para su control.</span><span class="sxs-lookup"><span data-stu-id="d9367-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="d9367-117">Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="d9367-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="d9367-118">Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="d9367-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="d9367-119">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="d9367-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9367-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9367-120">See also</span></span>

- [<span data-ttu-id="d9367-121">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="d9367-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="d9367-122">Cómo: Heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="d9367-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="d9367-123">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="d9367-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="d9367-124">Procedimientos: Controles de autor para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9367-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="d9367-125">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9367-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="d9367-126">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d9367-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
