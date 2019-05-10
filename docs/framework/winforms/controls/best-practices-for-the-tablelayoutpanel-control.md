---
title: Procedimientos recomendados para el control TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211353"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="56e83-102">Procedimientos recomendados para el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="56e83-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="56e83-103">El <xref:System.Windows.Forms.TableLayoutPanel> control proporciona eficaces características de diseño que se deben considerar cuidadosamente antes de usar en los formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="56e83-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>

## <a name="recommendations"></a><span data-ttu-id="56e83-104">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="56e83-104">Recommendations</span></span>
 <span data-ttu-id="56e83-105">Las recomendaciones siguientes le ayudarán a usar el <xref:System.Windows.Forms.TableLayoutPanel> control sacar el máximo partido.</span><span class="sxs-lookup"><span data-stu-id="56e83-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>

### <a name="targeted-use"></a><span data-ttu-id="56e83-106">Uso de destino</span><span class="sxs-lookup"><span data-stu-id="56e83-106">Targeted Use</span></span>
 <span data-ttu-id="56e83-107">Use el <xref:System.Windows.Forms.TableLayoutPanel> controlar con moderación.</span><span class="sxs-lookup"><span data-stu-id="56e83-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="56e83-108">No se debe usar en todas las situaciones que requieren un diseño de tamaño ajustable.</span><span class="sxs-lookup"><span data-stu-id="56e83-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="56e83-109">La siguiente lista describe los diseños que se beneficiarían del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:</span><span class="sxs-lookup"><span data-stu-id="56e83-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="56e83-110">Diseños en el que hay varias partes del formulario que cambian de tamaño proporcional entre sí.</span><span class="sxs-lookup"><span data-stu-id="56e83-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>

- <span data-ttu-id="56e83-111">Los diseños que se modificarán o generados dinámicamente en tiempo de ejecución, como formularios de entrada de datos que tienen campos personalizables por el usuario se suma o resta según las preferencias.</span><span class="sxs-lookup"><span data-stu-id="56e83-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>

- <span data-ttu-id="56e83-112">Diseños que deben permanecer en un tamaño fijo general.</span><span class="sxs-lookup"><span data-stu-id="56e83-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="56e83-113">Por ejemplo, puede tener un cuadro de diálogo debería ser menor que 800 x 600, pero tiene que admitir las cadenas localizadas.</span><span class="sxs-lookup"><span data-stu-id="56e83-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>

 <span data-ttu-id="56e83-114">La siguiente lista describe los diseños que no se benefician enormemente de utilizando el <xref:System.Windows.Forms.TableLayoutPanel> control:</span><span class="sxs-lookup"><span data-stu-id="56e83-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="56e83-115">Formularios de entrada de datos simple con una sola columna de etiquetas y una sola columna de áreas de entrada de texto.</span><span class="sxs-lookup"><span data-stu-id="56e83-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>

- <span data-ttu-id="56e83-116">Área que debería rellenar todo el espacio disponible cuando se produce un cambio de tamaño de presentación de formularios con una sola grande.</span><span class="sxs-lookup"><span data-stu-id="56e83-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="56e83-117">Un ejemplo de esto es un formulario que muestra una sola <xref:System.Windows.Forms.PropertyGrid> control.</span><span class="sxs-lookup"><span data-stu-id="56e83-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="56e83-118">En este caso, utilice el anclaje, porque nada debe expandir al tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="56e83-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>

 <span data-ttu-id="56e83-119">Elija cuidadosamente qué controles deben estar en un <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="56e83-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="56e83-120">Si tiene espacio para el texto para crecer en un 30% con delimitación, considere el uso de la <xref:System.Windows.Forms.Control.Anchor%2A> solo para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="56e83-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="56e83-121">Si se puede calcular el espacio requerido por su diseño, el uso de <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> es más fácil que calcular los detalles de espacio restante y <xref:System.Windows.Forms.Control.AutoSize%2A> comportamiento.</span><span class="sxs-lookup"><span data-stu-id="56e83-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>

 <span data-ttu-id="56e83-122">En general, al diseñar el diseño con el <xref:System.Windows.Forms.TableLayoutPanel> controlar, mantenga el diseño más simple posible.</span><span class="sxs-lookup"><span data-stu-id="56e83-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>

### <a name="use-the-document-outline-window"></a><span data-ttu-id="56e83-123">Utilice la ventana Esquema del documento</span><span class="sxs-lookup"><span data-stu-id="56e83-123">Use the Document Outline Window</span></span>
 <span data-ttu-id="56e83-124">La ventana Esquema del documento proporciona una vista de árbol de su diseño, lo que puede usar para manipular las relaciones de elementos primarios y secundarios y de orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="56e83-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="56e83-125">Desde el **menú Ver**, seleccione **Other Windows**, a continuación, seleccione **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="56e83-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>

### <a name="avoid-nesting"></a><span data-ttu-id="56e83-126">Evite el anidamiento</span><span class="sxs-lookup"><span data-stu-id="56e83-126">Avoid Nesting</span></span>
 <span data-ttu-id="56e83-127">Evite el anidamiento otro <xref:System.Windows.Forms.TableLayoutPanel> controla dentro de un <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="56e83-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="56e83-128">Puede ser difícil de depurar los diseños anidados.</span><span class="sxs-lookup"><span data-stu-id="56e83-128">Debugging nested layouts can be difficult.</span></span>

### <a name="avoid-visual-inheritance"></a><span data-ttu-id="56e83-129">Evite una herencia Visual</span><span class="sxs-lookup"><span data-stu-id="56e83-129">Avoid Visual Inheritance</span></span>
 <span data-ttu-id="56e83-130">El <xref:System.Windows.Forms.TableLayoutPanel> control no admite la herencia visual en el Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="56e83-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="56e83-131">Un <xref:System.Windows.Forms.TableLayoutPanel> aparezca el control en una clase derivada está "bloqueada" en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="56e83-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>

## <a name="see-also"></a><span data-ttu-id="56e83-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="56e83-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
