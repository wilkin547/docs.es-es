---
title: "Cómo: Heredar de una clase de control"
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
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 75b9c56d2d9df80745cec2b811c39f5e438d07c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="14842-102">Cómo: Heredar de una clase de control</span><span class="sxs-lookup"><span data-stu-id="14842-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="14842-103">Si desea crear un control completamente personalizado para utilizarlo en un formulario Windows Forms, debe heredar de la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="14842-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="14842-104">Al heredar de la <xref:System.Windows.Forms.Control> clase requiere que realice más planificación e implementación, también se proporciona con la mayor gama de opciones.</span><span class="sxs-lookup"><span data-stu-id="14842-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="14842-105">Al heredar de <xref:System.Windows.Forms.Control>, hereda la funcionalidad básica que hace funcionar los controles.</span><span class="sxs-lookup"><span data-stu-id="14842-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="14842-106">La funcionalidad inherente a la <xref:System.Windows.Forms.Control> clase controla proporcionados por el usuario a través del teclado y mouse (ratón), define los límites y el tamaño del control, proporciona un identificador de windows y proporciona control de mensajes y seguridad.</span><span class="sxs-lookup"><span data-stu-id="14842-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="14842-107">No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico.</span><span class="sxs-lookup"><span data-stu-id="14842-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="14842-108">Debe proporcionar todos estos elementos por medio del código personalizado.</span><span class="sxs-lookup"><span data-stu-id="14842-108">You must provide all of these aspects through custom code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14842-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="14842-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14842-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="14842-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14842-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="14842-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-custom-control"></a><span data-ttu-id="14842-112">Para crear un color personalizado</span><span class="sxs-lookup"><span data-stu-id="14842-112">To create a custom control</span></span>  
  
1.  <span data-ttu-id="14842-113">Cree un nuevo proyecto **Aplicación Windows** o **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="14842-113">Create a new **Windows Application** or **Windows Control Library** project.</span></span>  
  
2.  <span data-ttu-id="14842-114">En el menú **Proyecto**, elija **Agregar clase**.</span><span class="sxs-lookup"><span data-stu-id="14842-114">From the **Project** menu, choose **Add Class**.</span></span>  
  
3.  <span data-ttu-id="14842-115">En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="14842-115">In the **Add New Item** dialog box, click **Custom Control**.</span></span>  
  
     <span data-ttu-id="14842-116">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="14842-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="14842-117">Presione F7 para abrir el **Editor de código** para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="14842-117">Press F7 to open the **Code Editor** for your custom control.</span></span>  
  
5.  <span data-ttu-id="14842-118">Busque la <xref:System.Windows.Forms.Control.OnPaint%2A> método, que estará vacío salvo por una llamada a la <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base.</span><span class="sxs-lookup"><span data-stu-id="14842-118">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
6.  <span data-ttu-id="14842-119">Modifique el código para incorporar el dibujo personalizado que desee para su control.</span><span class="sxs-lookup"><span data-stu-id="14842-119">Modify the code to incorporate any custom painting you want for your control.</span></span>  
  
     <span data-ttu-id="14842-120">Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="14842-120">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
7.  <span data-ttu-id="14842-121">Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="14842-121">Implement any custom methods, properties, or events that your control will incorporate.</span></span>  
  
8.  <span data-ttu-id="14842-122">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="14842-122">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14842-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="14842-123">See Also</span></span>  
 [<span data-ttu-id="14842-124">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="14842-124">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="14842-125">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="14842-125">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="14842-126">Cómo: Heredar de controles de Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="14842-126">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="14842-127">Cómo: Crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="14842-127">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="14842-128">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="14842-128">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="14842-129">Desarrollar controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="14842-129">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
