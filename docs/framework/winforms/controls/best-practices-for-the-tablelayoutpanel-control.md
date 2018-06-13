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
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526458"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="0fc97-102">Procedimientos recomendados para el control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="0fc97-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="0fc97-103">El <xref:System.Windows.Forms.TableLayoutPanel> control proporciona eficaces características de diseño que se deben considerar cuidadosamente antes de usar en los formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0fc97-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="0fc97-104">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="0fc97-104">Recommendations</span></span>  
 <span data-ttu-id="0fc97-105">Las siguientes recomendaciones le ayudarán a usar el <xref:System.Windows.Forms.TableLayoutPanel> control su para aprovechar al máximo.</span><span class="sxs-lookup"><span data-stu-id="0fc97-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>  
  
### <a name="targeted-use"></a><span data-ttu-id="0fc97-106">Uso de destino</span><span class="sxs-lookup"><span data-stu-id="0fc97-106">Targeted Use</span></span>  
 <span data-ttu-id="0fc97-107">Use la <xref:System.Windows.Forms.TableLayoutPanel> controlar con moderación.</span><span class="sxs-lookup"><span data-stu-id="0fc97-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="0fc97-108">No se debe usar en todas las situaciones que requieren un diseño de tamaño variable.</span><span class="sxs-lookup"><span data-stu-id="0fc97-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="0fc97-109">En la lista siguiente describe los diseños que se beneficiarían del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:</span><span class="sxs-lookup"><span data-stu-id="0fc97-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="0fc97-110">Diseños en los que tienen varias partes del formulario que cambian el tamaño proporcionalmente entre sí.</span><span class="sxs-lookup"><span data-stu-id="0fc97-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>  
  
-   <span data-ttu-id="0fc97-111">Diseños que se pueden modificar ni se generó dinámicamente en tiempo de ejecución, como formularios de entrada de datos que tienen campos personalizables por el usuario agrega o resta según las preferencias.</span><span class="sxs-lookup"><span data-stu-id="0fc97-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>  
  
-   <span data-ttu-id="0fc97-112">Diseños que deberían permanecer en un tamaño fijo general.</span><span class="sxs-lookup"><span data-stu-id="0fc97-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="0fc97-113">Por ejemplo, puede tener un cuadro de diálogo que debería ser menor que 800 x 600, pero debe admitir las cadenas localizadas.</span><span class="sxs-lookup"><span data-stu-id="0fc97-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>  
  
 <span data-ttu-id="0fc97-114">En la lista siguiente se describe diseños que no se benefician en gran medida del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:</span><span class="sxs-lookup"><span data-stu-id="0fc97-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>  
  
-   <span data-ttu-id="0fc97-115">Formularios de entrada de datos simple con una única columna de etiquetas y una única columna de áreas de entrada de texto.</span><span class="sxs-lookup"><span data-stu-id="0fc97-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>  
  
-   <span data-ttu-id="0fc97-116">Área que debería rellenar todo el espacio disponible cuando se produce un cambio de tamaño de presentación de formularios con una sola grande.</span><span class="sxs-lookup"><span data-stu-id="0fc97-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="0fc97-117">Un ejemplo de esto es un formulario que muestra una sola <xref:System.Windows.Forms.PropertyGrid> control.</span><span class="sxs-lookup"><span data-stu-id="0fc97-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="0fc97-118">En este caso, utilice el anclaje, porque debería ampliar nada más cuando se cambia el tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="0fc97-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>  
  
 <span data-ttu-id="0fc97-119">Elija cuidadosamente qué controles deben estar en un <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="0fc97-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="0fc97-120">Si dispone de espacio para el texto que se va a crecer en 30% con delimitación, considere el uso de la <xref:System.Windows.Forms.Control.Anchor%2A> solo para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0fc97-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="0fc97-121">Si puede calcular el espacio requerido por su diseño, el uso de <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> es más fácil que calcular los detalles de espacio restante y <xref:System.Windows.Forms.Control.AutoSize%2A> comportamiento.</span><span class="sxs-lookup"><span data-stu-id="0fc97-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>  
  
 <span data-ttu-id="0fc97-122">En general, cuando use un diseño con el <xref:System.Windows.Forms.TableLayoutPanel> controlar, mantenga el diseño más sencilla posible.</span><span class="sxs-lookup"><span data-stu-id="0fc97-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>  
  
### <a name="use-the-document-outline-window"></a><span data-ttu-id="0fc97-123">Utilice la ventana Esquema del documento</span><span class="sxs-lookup"><span data-stu-id="0fc97-123">Use the Document Outline Window</span></span>  
 <span data-ttu-id="0fc97-124">La ventana Esquema del documento proporciona una vista de árbol de la distribución, que puede usar para manipular las relaciones de elementos primarios y secundarios y de orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="0fc97-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="0fc97-125">Desde el **menú Ver**, seleccione **otras ventanas**, a continuación, seleccione **esquema del documento**.</span><span class="sxs-lookup"><span data-stu-id="0fc97-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>  
  
### <a name="avoid-nesting"></a><span data-ttu-id="0fc97-126">Evite el anidamiento</span><span class="sxs-lookup"><span data-stu-id="0fc97-126">Avoid Nesting</span></span>  
 <span data-ttu-id="0fc97-127">Evite el anidamiento otro <xref:System.Windows.Forms.TableLayoutPanel> controla dentro de un <xref:System.Windows.Forms.TableLayoutPanel> control.</span><span class="sxs-lookup"><span data-stu-id="0fc97-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="0fc97-128">Depurar los diseños anidados puede resultar difícil.</span><span class="sxs-lookup"><span data-stu-id="0fc97-128">Debugging nested layouts can be difficult.</span></span>  
  
### <a name="avoid-visual-inheritance"></a><span data-ttu-id="0fc97-129">Evite una herencia Visual</span><span class="sxs-lookup"><span data-stu-id="0fc97-129">Avoid Visual Inheritance</span></span>  
 <span data-ttu-id="0fc97-130">El <xref:System.Windows.Forms.TableLayoutPanel> control no admite la herencia visual en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0fc97-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer.</span></span> <span data-ttu-id="0fc97-131">Un <xref:System.Windows.Forms.TableLayoutPanel> "bloqueada" en tiempo de diseño que aparezca el control en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0fc97-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc97-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fc97-132">See Also</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
