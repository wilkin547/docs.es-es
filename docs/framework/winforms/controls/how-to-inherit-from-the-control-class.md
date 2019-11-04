---
title: 'Cómo: Heredar de una clase de control'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 7af7d1fe8f14c71dfc90836d84023b98feb44961
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458384"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="0cbcf-102">Cómo: Heredar de una clase de control</span><span class="sxs-lookup"><span data-stu-id="0cbcf-102">How to: Inherit from the Control Class</span></span>

<span data-ttu-id="0cbcf-103">Si desea crear un control completamente personalizado para usarlo en Windows Forms, debe heredar de la clase <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="0cbcf-104">Aunque la herencia de la clase <xref:System.Windows.Forms.Control> requiere que realice más planeación e implementación, también proporciona la mayor variedad de opciones.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="0cbcf-105">Al heredar de <xref:System.Windows.Forms.Control>, hereda la funcionalidad muy básica que hace que los controles funcionen.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="0cbcf-106">La funcionalidad inherente en la clase <xref:System.Windows.Forms.Control> controla los datos proporcionados por el usuario a través del teclado y el mouse, define los límites y el tamaño del control, proporciona un identificador de Windows y proporciona seguridad y control de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="0cbcf-107">No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="0cbcf-108">Debe proporcionar todos estos elementos por medio del código personalizado.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="0cbcf-109">Para crear un color personalizado</span><span class="sxs-lookup"><span data-stu-id="0cbcf-109">To create a custom control</span></span>

1. <span data-ttu-id="0cbcf-110">En Visual Studio, cree una nueva **aplicación de Windows** o un proyecto de **biblioteca de controles de Windows** .</span><span class="sxs-lookup"><span data-stu-id="0cbcf-110">In Visual Studio, create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="0cbcf-111">En el menú **Proyecto**, elija **Agregar clase**.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="0cbcf-112">En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

   <span data-ttu-id="0cbcf-113">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="0cbcf-114">Presione **F7** para abrir el **Editor de código** para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-114">Press **F7** to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="0cbcf-115">Busque el método <xref:System.Windows.Forms.Control.OnPaint%2A>, que estará vacío excepto para una llamada al método <xref:System.Windows.Forms.Control.OnPaint%2A> de la clase base.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="0cbcf-116">Modifique el código para incorporar el dibujo personalizado que desee para su control.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

   <span data-ttu-id="0cbcf-117">Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="0cbcf-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="0cbcf-118">Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="0cbcf-119">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="0cbcf-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="0cbcf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cbcf-120">See also</span></span>

- [<span data-ttu-id="0cbcf-121">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="0cbcf-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="0cbcf-122">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="0cbcf-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="0cbcf-123">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="0cbcf-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="0cbcf-124">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0cbcf-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="0cbcf-125">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cbcf-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="0cbcf-126">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="0cbcf-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
