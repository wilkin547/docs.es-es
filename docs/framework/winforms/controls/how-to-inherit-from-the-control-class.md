---
title: Filtrar para heredar de la clase Control
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: b173f322018921ef1c0fec6aa785ae6c9d9e6957
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141991"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="640f4-102">Filtrar para heredar de la clase Control</span><span class="sxs-lookup"><span data-stu-id="640f4-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="640f4-103">Si desea crear un control completamente personalizado para usar en un formulario de Windows, debe heredar la <xref:System.Windows.Forms.Control> clase.</span><span class="sxs-lookup"><span data-stu-id="640f4-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="640f4-104">Al heredar el <xref:System.Windows.Forms.Control> clase requiere que realice más planeación e implementación, también proporciona con la mayor variedad de opciones.</span><span class="sxs-lookup"><span data-stu-id="640f4-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="640f4-105">Al heredar de <xref:System.Windows.Forms.Control>, hereda la funcionalidad básica que hace funcionar los controles.</span><span class="sxs-lookup"><span data-stu-id="640f4-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="640f4-106">La funcionalidad inherente a la <xref:System.Windows.Forms.Control> clase controla la entrada de usuario a través del teclado y mouse, define los límites y el tamaño del control, proporciona un identificador de windows y proporciona seguridad y control de mensajes.</span><span class="sxs-lookup"><span data-stu-id="640f4-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="640f4-107">No incorpora ningún dibujo, que en este caso es la representación real de la interfaz gráfica del control, ni cualquier funcionalidad de interacción de usuario específico.</span><span class="sxs-lookup"><span data-stu-id="640f4-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="640f4-108">Debe proporcionar todos estos elementos por medio del código personalizado.</span><span class="sxs-lookup"><span data-stu-id="640f4-108">You must provide all of these aspects through custom code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="640f4-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="640f4-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="640f4-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="640f4-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="640f4-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="640f4-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-custom-control"></a><span data-ttu-id="640f4-112">Para crear un color personalizado</span><span class="sxs-lookup"><span data-stu-id="640f4-112">To create a custom control</span></span>  
  
1.  <span data-ttu-id="640f4-113">Cree un nuevo proyecto **Aplicación Windows** o **Biblioteca de controles de Windows**.</span><span class="sxs-lookup"><span data-stu-id="640f4-113">Create a new **Windows Application** or **Windows Control Library** project.</span></span>  
  
2.  <span data-ttu-id="640f4-114">En el menú **Proyecto**, elija **Agregar clase**.</span><span class="sxs-lookup"><span data-stu-id="640f4-114">From the **Project** menu, choose **Add Class**.</span></span>  
  
3.  <span data-ttu-id="640f4-115">En el cuadro de diálogo **Agregar nuevo elemento**, haga clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="640f4-115">In the **Add New Item** dialog box, click **Custom Control**.</span></span>  
  
     <span data-ttu-id="640f4-116">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="640f4-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="640f4-117">Presione F7 para abrir el **Editor de código** para el control personalizado.</span><span class="sxs-lookup"><span data-stu-id="640f4-117">Press F7 to open the **Code Editor** for your custom control.</span></span>  
  
5.  <span data-ttu-id="640f4-118">Busque el <xref:System.Windows.Forms.Control.OnPaint%2A> método, que estará vacío salvo por una llamada a la <xref:System.Windows.Forms.Control.OnPaint%2A> método de la clase base.</span><span class="sxs-lookup"><span data-stu-id="640f4-118">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>  
  
6.  <span data-ttu-id="640f4-119">Modifique el código para incorporar el dibujo personalizado que desee para su control.</span><span class="sxs-lookup"><span data-stu-id="640f4-119">Modify the code to incorporate any custom painting you want for your control.</span></span>  
  
     <span data-ttu-id="640f4-120">Para información sobre cómo escribir código para representar gráficos para los controles, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="640f4-120">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>  
  
7.  <span data-ttu-id="640f4-121">Implemente los métodos, propiedades o eventos personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="640f4-121">Implement any custom methods, properties, or events that your control will incorporate.</span></span>  
  
8.  <span data-ttu-id="640f4-122">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="640f4-122">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640f4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="640f4-123">See also</span></span>

- [<span data-ttu-id="640f4-124">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="640f4-124">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="640f4-125">Filtrar para heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="640f4-125">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="640f4-126">Filtrar para heredar de controles de formularios Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="640f4-126">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="640f4-127">Filtrar para crear controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="640f4-127">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="640f4-128">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="640f4-128">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="640f4-129">Desarrollar controles de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="640f4-129">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
