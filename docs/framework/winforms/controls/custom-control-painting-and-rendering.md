---
title: Dibujo y representación personalizados de controles
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 14abac5678bfffa3cdb61307fd3cb54681c82a99
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506087"
---
# <a name="custom-control-painting-and-rendering"></a><span data-ttu-id="203d3-102">Dibujo y representación personalizados de controles</span><span class="sxs-lookup"><span data-stu-id="203d3-102">Custom Control Painting and Rendering</span></span>
<span data-ttu-id="203d3-103">Dibujo personalizado de controles es una de las muchas tareas complicadas fáciles mediante .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="203d3-103">Custom painting of controls is one of the many complicated tasks made easy by the .NET Framework.</span></span> <span data-ttu-id="203d3-104">Al crear un control personalizado, tiene muchas opciones con respecto a la apariencia gráfica del control.</span><span class="sxs-lookup"><span data-stu-id="203d3-104">When authoring a custom control, you have many options regarding your control's graphical appearance.</span></span> <span data-ttu-id="203d3-105">Si va a crear un control que hereda de la `Control`, debe proporcionar código que permita el control representar su representación gráfica.</span><span class="sxs-lookup"><span data-stu-id="203d3-105">If you are authoring a control that inherits from the `Control`, you must provide code that allows your control to render its graphical representation.</span></span> <span data-ttu-id="203d3-106">Si va a crear un control de usuario que se herede de la `UserControl`, o se hereda desde uno de los controles de Windows Forms, puede reemplazar la representación gráfica estándar y proporcionar su propio código de gráficos.</span><span class="sxs-lookup"><span data-stu-id="203d3-106">If you are creating a user control by inheriting from the `UserControl`, or are inheriting from one of the Windows Forms controls, you may override the standard graphical representation and provide your own graphics code.</span></span> <span data-ttu-id="203d3-107">Si desea proporcionar una representación personalizada para los controles constituyentes de una `UserControl` va a crear, las opciones se convierten en más limitadas, pero aún permiten una amplia gama de posibilidades gráficas para los controles y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="203d3-107">If you want to provide custom rendering for the constituent controls of a `UserControl` you are authoring, your options become more limited, but still allow a wide range of graphical possibilities for your controls and applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="203d3-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="203d3-108">In This Section</span></span>  
 [<span data-ttu-id="203d3-109">Representar un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="203d3-109">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)  
 <span data-ttu-id="203d3-110">Muestra cómo programar la lógica que muestra un control.</span><span class="sxs-lookup"><span data-stu-id="203d3-110">Shows how to program the logic that displays a control.</span></span>  
  
 [<span data-ttu-id="203d3-111">Controles dibujados por el usuario</span><span class="sxs-lookup"><span data-stu-id="203d3-111">User-Drawn Controls</span></span>](user-drawn-controls.md)  
 <span data-ttu-id="203d3-112">Proporciona información general de los pasos necesarios para escribir y reemplazar código de representación para el control.</span><span class="sxs-lookup"><span data-stu-id="203d3-112">Gives an overview of the steps involved in writing and overriding rendering code for your control.</span></span>  
  
 [<span data-ttu-id="203d3-113">Controles constituyentes</span><span class="sxs-lookup"><span data-stu-id="203d3-113">Constituent Controls</span></span>](constituent-controls.md)  
 <span data-ttu-id="203d3-114">Describe cómo implementar el código de representación personalizadas para controles constituyentes en los controles de usuario y los formularios.</span><span class="sxs-lookup"><span data-stu-id="203d3-114">Describes how to implement custom rendering code for constituent controls in your user controls and forms.</span></span>  
  
 [<span data-ttu-id="203d3-115">Cómo: Hacer que el Control Invisible en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="203d3-115">How to: Make Your Control Invisible at Run Time</span></span>](how-to-make-your-control-invisible-at-run-time.md)  
 <span data-ttu-id="203d3-116">Se muestra cómo usar el <xref:System.Windows.Forms.Control.Visible%2A> propiedad para ocultar y mostrar un control.</span><span class="sxs-lookup"><span data-stu-id="203d3-116">Shows how to use the <xref:System.Windows.Forms.Control.Visible%2A> property to hide and show a control.</span></span>  
  
 [<span data-ttu-id="203d3-117">Cómo: Proporcionar un fondo transparente a un Control</span><span class="sxs-lookup"><span data-stu-id="203d3-117">How to: Give Your Control a Transparent Background</span></span>](how-to-give-your-control-a-transparent-background.md)  
 <span data-ttu-id="203d3-118">Se muestra cómo usar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para crear un color de fondo opaco, transparente o parcialmente transparentes.</span><span class="sxs-lookup"><span data-stu-id="203d3-118">Shows how to use the <xref:System.Windows.Forms.Control.SetStyle%2A> method to create a background color that is opaque, transparent, or partially transparent.</span></span>  
  
 [<span data-ttu-id="203d3-119">Representar controles con estilos visuales</span><span class="sxs-lookup"><span data-stu-id="203d3-119">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)  
 <span data-ttu-id="203d3-120">Muestra cómo representar controles con estilos visuales en sistemas operativos compatibles con ellos.</span><span class="sxs-lookup"><span data-stu-id="203d3-120">Shows how to render controls using visual styles in operating systems that support them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="203d3-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="203d3-121">Reference</span></span>  
 <xref:System.Windows.Forms.Control>  
 <span data-ttu-id="203d3-122">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="203d3-122">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl>  
 <span data-ttu-id="203d3-123">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="203d3-123">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <span data-ttu-id="203d3-124">Se describe este método.</span><span class="sxs-lookup"><span data-stu-id="203d3-124">Describes this method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="203d3-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="203d3-125">Related Sections</span></span>  
 [<span data-ttu-id="203d3-126">Cómo: Crear objetos Graphics para dibujar</span><span class="sxs-lookup"><span data-stu-id="203d3-126">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 <span data-ttu-id="203d3-127">Presenta la funcionalidad de gráficos GDI + desde la perspectiva de Visual Studio y proporciona vínculos a información adicional.</span><span class="sxs-lookup"><span data-stu-id="203d3-127">Introduces GDI+ graphics functionality from a Visual Studio perspective and gives links to more information.</span></span>  
  
 [<span data-ttu-id="203d3-128">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="203d3-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="203d3-129">Describe los tipos de controles personalizados que puede crear.</span><span class="sxs-lookup"><span data-stu-id="203d3-129">Describes the kinds of custom controls you can author.</span></span>
