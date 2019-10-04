---
title: 'Tutorial: Crear una aplicación accesible basada en Windows'
ms.date: 03/30/2017
helpviewer_keywords:
- accessibility [Windows Forms], Windows applications
- Windows applications [Windows Forms], accessibility
- applications [Windows Forms], accessibility
dev_langs:
- csharp
- vb
ms.assetid: 654c7f2f-1586-480b-9f12-9d9b8f5cc32b
ms.openlocfilehash: b8f0c7c4584505d382e78aca68e2e99c9fa7748f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834626"
---
# <a name="walkthrough-creating-an-accessible-windows-based-application"></a><span data-ttu-id="a74a1-102">Tutorial: Crear una aplicación accesible basada en Windows</span><span class="sxs-lookup"><span data-stu-id="a74a1-102">Walkthrough: Creating an Accessible Windows-based Application</span></span>

<span data-ttu-id="a74a1-103">Crear una aplicación accesible conlleva importantes implicaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="a74a1-103">Creating an accessible application has important business implications.</span></span> <span data-ttu-id="a74a1-104">Muchos gobiernos tienen normativas sobre accesibilidad aplicadas a la compra de software.</span><span class="sxs-lookup"><span data-stu-id="a74a1-104">Many governments have accessibility regulations for software purchase.</span></span> <span data-ttu-id="a74a1-105">El logotipo “Certificado para Windows” incluye requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a74a1-105">The Certified for Windows logo includes accessibility requirements.</span></span> <span data-ttu-id="a74a1-106">Tan solo en EE. UU hay aproximadamente unos 30 millones de ciudadanos, muchos de ellos clientes potenciales, que se ven afectados por la accesibilidad del software.</span><span class="sxs-lookup"><span data-stu-id="a74a1-106">An estimated 30 million residents of the U.S. alone, many of them potential customers, are affected by the accessibility of software.</span></span>

<span data-ttu-id="a74a1-107">En este tutorial se tratan los cinco requisitos de accesibilidad para el logotipo “Certificado para Windows”.</span><span class="sxs-lookup"><span data-stu-id="a74a1-107">This walkthrough will address the five accessibility requirements for the Certified for Windows logo.</span></span> <span data-ttu-id="a74a1-108">Según estos requisitos, una aplicación accesible deberá:</span><span class="sxs-lookup"><span data-stu-id="a74a1-108">According to these requirements, an accessible application will:</span></span>

- <span data-ttu-id="a74a1-109">Admitir la configuración de la entrada, la fuente, el color y el tamaño en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a74a1-109">Support Control Panel size, color, font, and input settings.</span></span> <span data-ttu-id="a74a1-110">La barra de menús, la barra de título, los bordes y la barra de estado cambiarán de tamaño cuando el usuario cambie la configuración del Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a74a1-110">The menu bar, title bar, borders, and status bar will all resize themselves when the user changes the control panel settings.</span></span> <span data-ttu-id="a74a1-111">No se requiere ningún otro cambio en los controles o el código en esta aplicación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-111">No additional changes to the controls or code are required in this application.</span></span>

- <span data-ttu-id="a74a1-112">Admitir el modo de contraste alto.</span><span class="sxs-lookup"><span data-stu-id="a74a1-112">Support High Contrast mode.</span></span>

- <span data-ttu-id="a74a1-113">Proporcionar acceso mediante teclado a todas las características (y documentarlo).</span><span class="sxs-lookup"><span data-stu-id="a74a1-113">Provide documented keyboard access to all features.</span></span>

- <span data-ttu-id="a74a1-114">Exponer la ubicación del foco del teclado de manera visual y mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-114">Expose location of the keyboard focus visually and programmatically.</span></span>

- <span data-ttu-id="a74a1-115">Evitar ofrecer información importante solo mediante sonido.</span><span class="sxs-lookup"><span data-stu-id="a74a1-115">Avoid conveying important information by sound alone.</span></span>

<span data-ttu-id="a74a1-116">Para más información, consulte [Recursos para diseñar aplicaciones accesibles](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span><span class="sxs-lookup"><span data-stu-id="a74a1-116">For more information, see [Resources for Designing Accessible Applications](/visualstudio/ide/reference/resources-for-designing-accessible-applications).</span></span>

<span data-ttu-id="a74a1-117">Para información sobre la compatibilidad con diversas distribuciones de teclado, consulte [Procedimientos recomendados para desarrollar aplicaciones de uso internacional](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a74a1-117">For information on supporting varying keyboard layouts, see [Best Practices for Developing World-Ready Applications](../../../standard/globalization-localization/best-practices-for-developing-world-ready-apps.md).</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="a74a1-118">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="a74a1-118">Creating the Project</span></span>

<span data-ttu-id="a74a1-119">En este tutorial se crea la interfaz de usuario de una aplicación que admite pedidos de pizzas.</span><span class="sxs-lookup"><span data-stu-id="a74a1-119">This walkthrough creates the user interface for an application that takes pizza orders.</span></span> <span data-ttu-id="a74a1-120">La interfaz consta de un <xref:System.Windows.Forms.TextBox> para el nombre del cliente, un grupo <xref:System.Windows.Forms.RadioButton> para seleccionar el tamaño de la pizza, un <xref:System.Windows.Forms.CheckedListBox> para seleccionar los ingredientes, dos controles de botón (Button) con la etiqueta Order y Cancel y un menú con un comando Exit.</span><span class="sxs-lookup"><span data-stu-id="a74a1-120">It consists of a <xref:System.Windows.Forms.TextBox> for the customer's name, a <xref:System.Windows.Forms.RadioButton> group to select the pizza size, a <xref:System.Windows.Forms.CheckedListBox> for selecting the toppings, two Button controls labeled Order and Cancel, and a Menu with an Exit command.</span></span>

<span data-ttu-id="a74a1-121">El usuario escribe el nombre del cliente, el tamaño de la pizza y los ingredientes que desea.</span><span class="sxs-lookup"><span data-stu-id="a74a1-121">The user enters the customer's name, the size of the pizza, and the toppings desired.</span></span> <span data-ttu-id="a74a1-122">Cuando el usuario hace clic en el botón Order, aparece un cuadro de mensaje con un resumen del pedido y su costo, y los controles se borran y quedan listos para el siguiente pedido.</span><span class="sxs-lookup"><span data-stu-id="a74a1-122">When the user clicks the Order button, a summary of the order and its cost are displayed in a message box and the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="a74a1-123">Cuando el usuario hace clic en el botón Cancelar, los controles se borran y quedan listos para el siguiente pedido.</span><span class="sxs-lookup"><span data-stu-id="a74a1-123">When the user clicks the Cancel button, the controls are cleared and ready for the next order.</span></span> <span data-ttu-id="a74a1-124">Cuando el usuario hace clic en el elemento de menú Exit, el programa se cierra.</span><span class="sxs-lookup"><span data-stu-id="a74a1-124">When the user clicks the Exit menu item, the program closes.</span></span>

<span data-ttu-id="a74a1-125">El énfasis de este tutorial no recae en el código para un sistema de pedidos de venta directa, sino en la accesibilidad de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a74a1-125">The emphasis of this walkthrough is not the code for a retail order system, but the accessibility of the user interface.</span></span> <span data-ttu-id="a74a1-126">En el tutorial se muestran las características de accesibilidad de varios controles de uso frecuente, como botones, botones de radio, cuadros de texto y etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a74a1-126">The walkthrough demonstrates the accessibility features of several frequently used controls, including buttons, radio buttons, text boxes, and labels.</span></span>

#### <a name="to-begin-making-the-application"></a><span data-ttu-id="a74a1-127">Para comenzar a crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="a74a1-127">To begin making the application</span></span>

- <span data-ttu-id="a74a1-128">Cree una nueva aplicación de Windows en Visual Basic o C#visual.</span><span class="sxs-lookup"><span data-stu-id="a74a1-128">Create a new Windows Application in Visual Basic or Visual C#.</span></span> <span data-ttu-id="a74a1-129">Asigne al proyecto el nombre **PizzaOrder**.</span><span class="sxs-lookup"><span data-stu-id="a74a1-129">Name the project **PizzaOrder**.</span></span> <span data-ttu-id="a74a1-130">Para obtener más información, vea [crear nuevas soluciones y proyectos](/visualstudio/ide/creating-solutions-and-projects).</span><span class="sxs-lookup"><span data-stu-id="a74a1-130">For details, see [Creating New Solutions and Projects](/visualstudio/ide/creating-solutions-and-projects).</span></span>

## <a name="adding-the-controls-to-the-form"></a><span data-ttu-id="a74a1-131">Agregar controles al formulario</span><span class="sxs-lookup"><span data-stu-id="a74a1-131">Adding the Controls to the Form</span></span>

<span data-ttu-id="a74a1-132">Cuando agregue controles a un formulario, tenga en cuenta las siguientes instrucciones para crear una aplicación accesible:</span><span class="sxs-lookup"><span data-stu-id="a74a1-132">When adding the controls to a form, keep in mind the following guidelines to make an accessible application:</span></span>

- <span data-ttu-id="a74a1-133">Establezca las propiedades <xref:System.Windows.Forms.Control.AccessibleDescription%2A> y <xref:System.Windows.Forms.Control.AccessibleName%2A>.</span><span class="sxs-lookup"><span data-stu-id="a74a1-133">Set the <xref:System.Windows.Forms.Control.AccessibleDescription%2A> and <xref:System.Windows.Forms.Control.AccessibleName%2A> properties.</span></span> <span data-ttu-id="a74a1-134">En este ejemplo, la configuración predeterminada para <xref:System.Windows.Forms.Control.AccessibleRole%2A> es suficiente.</span><span class="sxs-lookup"><span data-stu-id="a74a1-134">In this example, the Default setting for the <xref:System.Windows.Forms.Control.AccessibleRole%2A> is sufficient.</span></span> <span data-ttu-id="a74a1-135">Para más información sobre las propiedades de accesibilidad, consulte [Proporcionar información de accesibilidad de controles en Windows Forms](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="a74a1-135">For more information on the accessibility properties, see [Providing Accessibility Information for Controls on a Windows Form](../controls/providing-accessibility-information-for-controls-on-a-windows-form.md).</span></span>

- <span data-ttu-id="a74a1-136">Establezca el tamaño de la fuente en 10 puntos o más.</span><span class="sxs-lookup"><span data-stu-id="a74a1-136">Set the font size to 10 points or larger.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a74a1-137">Si establece el tamaño de la fuente del formulario en 10 al empezar, todos los controles que agregue posteriormente al formulario tendrán un tamaño de fuente de 10.</span><span class="sxs-lookup"><span data-stu-id="a74a1-137">If you set the font size of the form to 10 when you start, then all controls subsequently added to the form will have a font size of 10.</span></span>

- <span data-ttu-id="a74a1-138">Asegúrese de que los controles Label que describen controles TextBox precedan inmediatamente al TextBox en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-138">Make sure any Label control that describes a TextBox control immediately precedes the TextBox control in the tab order.</span></span>

- <span data-ttu-id="a74a1-139">Agregue una tecla de acceso, utilizando el carácter "&", a <xref:System.Windows.Forms.Control.Text%2A> la propiedad de cualquier control al que el usuario desee navegar.</span><span class="sxs-lookup"><span data-stu-id="a74a1-139">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of any control the user may want to navigate to.</span></span>

- <span data-ttu-id="a74a1-140">Agregue una tecla de acceso, utilizando el carácter "&", a <xref:System.Windows.Forms.Control.Text%2A> la propiedad de la etiqueta que precede a un control al que el usuario puede desear navegar.</span><span class="sxs-lookup"><span data-stu-id="a74a1-140">Add an access key, using the "&" character, to the <xref:System.Windows.Forms.Control.Text%2A> property of the label that precedes a control that the user may want to navigate to.</span></span> <span data-ttu-id="a74a1-141">Establezca la propiedad <xref:System.Windows.Forms.Label.UseMnemonic%2A> de las etiquetas en `true`, de modo que el foco se centre en el siguiente control del orden de tabulación cuando el usuario presione la tecla de acceso.</span><span class="sxs-lookup"><span data-stu-id="a74a1-141">Set the labels' <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`, so that the focus is set to the next control in the tab order when the user presses the access key.</span></span>

- <span data-ttu-id="a74a1-142">Agregue teclas de acceso a todos los elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="a74a1-142">Add access keys to all menu items.</span></span>

#### <a name="to-make-your-windows-application-accessible"></a><span data-ttu-id="a74a1-143">Para hacer accesible la aplicación Windows</span><span class="sxs-lookup"><span data-stu-id="a74a1-143">To make your Windows Application accessible</span></span>

- <span data-ttu-id="a74a1-144">Agregue los controles al formulario y establezca las propiedades como se describe a continuación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-144">Add the controls to the form and set the properties as described below.</span></span> <span data-ttu-id="a74a1-145">Consulte la imagen al final de la tabla para ver un modelo de cómo organizar los controles en el formulario.</span><span class="sxs-lookup"><span data-stu-id="a74a1-145">See the picture at the end of the table for a model of how to arrange the controls on the form.</span></span>

   |<span data-ttu-id="a74a1-146">Object</span><span class="sxs-lookup"><span data-stu-id="a74a1-146">Object</span></span>|<span data-ttu-id="a74a1-147">Property</span><span class="sxs-lookup"><span data-stu-id="a74a1-147">Property</span></span>|<span data-ttu-id="a74a1-148">Valor</span><span class="sxs-lookup"><span data-stu-id="a74a1-148">Value</span></span>|
   |------------|--------------|-----------|
   |<span data-ttu-id="a74a1-149">Form1</span><span class="sxs-lookup"><span data-stu-id="a74a1-149">Form1</span></span>|<span data-ttu-id="a74a1-150">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-150">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-151">Formulario de pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-151">Order form</span></span>|
   ||<span data-ttu-id="a74a1-152">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-152">AccessibleName</span></span>|<span data-ttu-id="a74a1-153">Formulario de pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-153">Order form</span></span>|
   ||<span data-ttu-id="a74a1-154">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="a74a1-154">Font Size</span></span>|<span data-ttu-id="a74a1-155">10</span><span class="sxs-lookup"><span data-stu-id="a74a1-155">10</span></span>|
   ||<span data-ttu-id="a74a1-156">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-156">Text</span></span>|<span data-ttu-id="a74a1-157">Pizza Order Form</span><span class="sxs-lookup"><span data-stu-id="a74a1-157">Pizza Order Form</span></span>|
   |<span data-ttu-id="a74a1-158">PictureBox</span><span class="sxs-lookup"><span data-stu-id="a74a1-158">PictureBox</span></span>|<span data-ttu-id="a74a1-159">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-159">Name</span></span>|<span data-ttu-id="a74a1-160">logo</span><span class="sxs-lookup"><span data-stu-id="a74a1-160">logo</span></span>|
   ||<span data-ttu-id="a74a1-161">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-161">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-162">Porción de pizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-162">A slice of pizza</span></span>|
   ||<span data-ttu-id="a74a1-163">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-163">AccessibleName</span></span>|<span data-ttu-id="a74a1-164">Logotipo de la compañía</span><span class="sxs-lookup"><span data-stu-id="a74a1-164">Company logo</span></span>|
   ||<span data-ttu-id="a74a1-165">Image</span><span class="sxs-lookup"><span data-stu-id="a74a1-165">Image</span></span>|<span data-ttu-id="a74a1-166">Cualquier icono o mapa de bits</span><span class="sxs-lookup"><span data-stu-id="a74a1-166">Any icon or bitmap</span></span>|
   |<span data-ttu-id="a74a1-167">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a74a1-167">Label</span></span>|<span data-ttu-id="a74a1-168">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-168">Name</span></span>|<span data-ttu-id="a74a1-169">companyLabel</span><span class="sxs-lookup"><span data-stu-id="a74a1-169">companyLabel</span></span>|
   ||<span data-ttu-id="a74a1-170">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-170">Text</span></span>|<span data-ttu-id="a74a1-171">Good Pizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-171">Good Pizza</span></span>|
   ||<span data-ttu-id="a74a1-172">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-172">TabIndex</span></span>|<span data-ttu-id="a74a1-173">1</span><span class="sxs-lookup"><span data-stu-id="a74a1-173">1</span></span>|
   ||<span data-ttu-id="a74a1-174">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-174">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-175">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="a74a1-175">Company name</span></span>|
   ||<span data-ttu-id="a74a1-176">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-176">AccessibleName</span></span>|<span data-ttu-id="a74a1-177">Nombre de la compañía</span><span class="sxs-lookup"><span data-stu-id="a74a1-177">Company name</span></span>|
   ||<span data-ttu-id="a74a1-178">Backcolor</span><span class="sxs-lookup"><span data-stu-id="a74a1-178">Backcolor</span></span>|<span data-ttu-id="a74a1-179">Azul</span><span class="sxs-lookup"><span data-stu-id="a74a1-179">Blue</span></span>|
   ||<span data-ttu-id="a74a1-180">Forecolor</span><span class="sxs-lookup"><span data-stu-id="a74a1-180">Forecolor</span></span>|<span data-ttu-id="a74a1-181">Amarillo</span><span class="sxs-lookup"><span data-stu-id="a74a1-181">Yellow</span></span>|
   ||<span data-ttu-id="a74a1-182">Tamaño de fuente</span><span class="sxs-lookup"><span data-stu-id="a74a1-182">Font size</span></span>|<span data-ttu-id="a74a1-183">18</span><span class="sxs-lookup"><span data-stu-id="a74a1-183">18</span></span>|
   |<span data-ttu-id="a74a1-184">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a74a1-184">Label</span></span>|<span data-ttu-id="a74a1-185">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-185">Name</span></span>|<span data-ttu-id="a74a1-186">customerLabel</span><span class="sxs-lookup"><span data-stu-id="a74a1-186">customerLabel</span></span>|
   ||<span data-ttu-id="a74a1-187">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-187">Text</span></span>|<span data-ttu-id="a74a1-188">&Nombre</span><span class="sxs-lookup"><span data-stu-id="a74a1-188">&Name</span></span>|
   ||<span data-ttu-id="a74a1-189">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-189">TabIndex</span></span>|<span data-ttu-id="a74a1-190">2</span><span class="sxs-lookup"><span data-stu-id="a74a1-190">2</span></span>|
   ||<span data-ttu-id="a74a1-191">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-191">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-192">Etiqueta de nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="a74a1-192">Customer name label</span></span>|
   ||<span data-ttu-id="a74a1-193">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-193">AccessibleName</span></span>|<span data-ttu-id="a74a1-194">Etiqueta de nombre de cliente</span><span class="sxs-lookup"><span data-stu-id="a74a1-194">Customer name label</span></span>|
   ||<span data-ttu-id="a74a1-195">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="a74a1-195">UseMnemonic</span></span>|<span data-ttu-id="a74a1-196">True</span><span class="sxs-lookup"><span data-stu-id="a74a1-196">True</span></span>|
   |<span data-ttu-id="a74a1-197">TextBox</span><span class="sxs-lookup"><span data-stu-id="a74a1-197">TextBox</span></span>|<span data-ttu-id="a74a1-198">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-198">Name</span></span>|<span data-ttu-id="a74a1-199">customerName</span><span class="sxs-lookup"><span data-stu-id="a74a1-199">customerName</span></span>|
   ||<span data-ttu-id="a74a1-200">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-200">Text</span></span>|<span data-ttu-id="a74a1-201">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="a74a1-201">(none)</span></span>|
   ||<span data-ttu-id="a74a1-202">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-202">TabIndex</span></span>|<span data-ttu-id="a74a1-203">3</span><span class="sxs-lookup"><span data-stu-id="a74a1-203">3</span></span>|
   ||<span data-ttu-id="a74a1-204">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-204">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-205">Nombre del cliente</span><span class="sxs-lookup"><span data-stu-id="a74a1-205">Customer name</span></span>|
   ||<span data-ttu-id="a74a1-206">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-206">AccessibleName</span></span>|<span data-ttu-id="a74a1-207">Nombre del cliente</span><span class="sxs-lookup"><span data-stu-id="a74a1-207">Customer name</span></span>|
   |<span data-ttu-id="a74a1-208">GroupBox</span><span class="sxs-lookup"><span data-stu-id="a74a1-208">GroupBox</span></span>|<span data-ttu-id="a74a1-209">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-209">Name</span></span>|<span data-ttu-id="a74a1-210">sizeOptions</span><span class="sxs-lookup"><span data-stu-id="a74a1-210">sizeOptions</span></span>|
   ||<span data-ttu-id="a74a1-211">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-211">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-212">Opciones de tamaño de pizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-212">Pizza size options</span></span>|
   ||<span data-ttu-id="a74a1-213">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-213">AccessibleName</span></span>|<span data-ttu-id="a74a1-214">Opciones de tamaño de pizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-214">Pizza size options</span></span>|
   ||<span data-ttu-id="a74a1-215">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-215">Text</span></span>|<span data-ttu-id="a74a1-216">Pizza size</span><span class="sxs-lookup"><span data-stu-id="a74a1-216">Pizza size</span></span>|
   ||<span data-ttu-id="a74a1-217">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-217">TabIndex</span></span>|<span data-ttu-id="a74a1-218">4</span><span class="sxs-lookup"><span data-stu-id="a74a1-218">4</span></span>|
   |<span data-ttu-id="a74a1-219">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a74a1-219">RadioButton</span></span>|<span data-ttu-id="a74a1-220">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-220">Name</span></span>|<span data-ttu-id="a74a1-221">smallPizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-221">smallPizza</span></span>|
   ||<span data-ttu-id="a74a1-222">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-222">Text</span></span>|<span data-ttu-id="a74a1-223">&Small $6.00</span><span class="sxs-lookup"><span data-stu-id="a74a1-223">&Small $6.00</span></span>|
   ||<span data-ttu-id="a74a1-224">Activado</span><span class="sxs-lookup"><span data-stu-id="a74a1-224">Checked</span></span>|<span data-ttu-id="a74a1-225">True</span><span class="sxs-lookup"><span data-stu-id="a74a1-225">True</span></span>|
   ||<span data-ttu-id="a74a1-226">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-226">TabIndex</span></span>|<span data-ttu-id="a74a1-227">0</span><span class="sxs-lookup"><span data-stu-id="a74a1-227">0</span></span>|
   ||<span data-ttu-id="a74a1-228">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-228">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-229">Pizza pequeña</span><span class="sxs-lookup"><span data-stu-id="a74a1-229">Small pizza</span></span>|
   ||<span data-ttu-id="a74a1-230">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-230">AccessibleName</span></span>|<span data-ttu-id="a74a1-231">Pizza pequeña</span><span class="sxs-lookup"><span data-stu-id="a74a1-231">Small pizza</span></span>|
   |<span data-ttu-id="a74a1-232">RadioButton</span><span class="sxs-lookup"><span data-stu-id="a74a1-232">RadioButton</span></span>|<span data-ttu-id="a74a1-233">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-233">Name</span></span>|<span data-ttu-id="a74a1-234">largePizza</span><span class="sxs-lookup"><span data-stu-id="a74a1-234">largePizza</span></span>|
   ||<span data-ttu-id="a74a1-235">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-235">Text</span></span>|<span data-ttu-id="a74a1-236">&Large $10.00</span><span class="sxs-lookup"><span data-stu-id="a74a1-236">&Large $10.00</span></span>|
   ||<span data-ttu-id="a74a1-237">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-237">TabIndex</span></span>|<span data-ttu-id="a74a1-238">1</span><span class="sxs-lookup"><span data-stu-id="a74a1-238">1</span></span>|
   ||<span data-ttu-id="a74a1-239">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-239">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-240">Pizza grande</span><span class="sxs-lookup"><span data-stu-id="a74a1-240">Large pizza</span></span>|
   ||<span data-ttu-id="a74a1-241">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-241">AccessibleName</span></span>|<span data-ttu-id="a74a1-242">Pizza grande</span><span class="sxs-lookup"><span data-stu-id="a74a1-242">Large pizza</span></span>|
   |<span data-ttu-id="a74a1-243">Etiqueta</span><span class="sxs-lookup"><span data-stu-id="a74a1-243">Label</span></span>|<span data-ttu-id="a74a1-244">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-244">Name</span></span>|<span data-ttu-id="a74a1-245">toppingsLabel</span><span class="sxs-lookup"><span data-stu-id="a74a1-245">toppingsLabel</span></span>|
   ||<span data-ttu-id="a74a1-246">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-246">Text</span></span>|<span data-ttu-id="a74a1-247">&Toppings ($0.75 each)</span><span class="sxs-lookup"><span data-stu-id="a74a1-247">&Toppings ($0.75 each)</span></span>|
   ||<span data-ttu-id="a74a1-248">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-248">TabIndex</span></span>|<span data-ttu-id="a74a1-249">5</span><span class="sxs-lookup"><span data-stu-id="a74a1-249">5</span></span>|
   ||<span data-ttu-id="a74a1-250">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-250">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-251">Etiqueta de ingredientes</span><span class="sxs-lookup"><span data-stu-id="a74a1-251">Toppings label</span></span>|
   ||<span data-ttu-id="a74a1-252">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-252">AccessibleName</span></span>|<span data-ttu-id="a74a1-253">Etiqueta de ingredientes</span><span class="sxs-lookup"><span data-stu-id="a74a1-253">Toppings label</span></span>|
   ||<span data-ttu-id="a74a1-254">UseMnemonic</span><span class="sxs-lookup"><span data-stu-id="a74a1-254">UseMnemonic</span></span>|<span data-ttu-id="a74a1-255">True</span><span class="sxs-lookup"><span data-stu-id="a74a1-255">True</span></span>|
   |<span data-ttu-id="a74a1-256">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="a74a1-256">CheckedListBox</span></span>|<span data-ttu-id="a74a1-257">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-257">Name</span></span>|<span data-ttu-id="a74a1-258">toppings</span><span class="sxs-lookup"><span data-stu-id="a74a1-258">toppings</span></span>|
   ||<span data-ttu-id="a74a1-259">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-259">TabIndex</span></span>|<span data-ttu-id="a74a1-260">6</span><span class="sxs-lookup"><span data-stu-id="a74a1-260">6</span></span>|
   ||<span data-ttu-id="a74a1-261">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-261">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-262">Ingredientes disponibles</span><span class="sxs-lookup"><span data-stu-id="a74a1-262">Available toppings</span></span>|
   ||<span data-ttu-id="a74a1-263">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-263">AccessibleName</span></span>|<span data-ttu-id="a74a1-264">Ingredientes disponibles</span><span class="sxs-lookup"><span data-stu-id="a74a1-264">Available toppings</span></span>|
   ||<span data-ttu-id="a74a1-265">Elementos</span><span class="sxs-lookup"><span data-stu-id="a74a1-265">Items</span></span>|<span data-ttu-id="a74a1-266">Pepperoni, Sausage, Mushrooms</span><span class="sxs-lookup"><span data-stu-id="a74a1-266">Pepperoni, Sausage, Mushrooms</span></span>|
   |<span data-ttu-id="a74a1-267">Botón</span><span class="sxs-lookup"><span data-stu-id="a74a1-267">Button</span></span>|<span data-ttu-id="a74a1-268">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-268">Name</span></span>|<span data-ttu-id="a74a1-269">orden</span><span class="sxs-lookup"><span data-stu-id="a74a1-269">order</span></span>|
   ||<span data-ttu-id="a74a1-270">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-270">Text</span></span>|<span data-ttu-id="a74a1-271">&Ordenar</span><span class="sxs-lookup"><span data-stu-id="a74a1-271">&Order</span></span>|
   ||<span data-ttu-id="a74a1-272">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-272">TabIndex</span></span>|<span data-ttu-id="a74a1-273">7</span><span class="sxs-lookup"><span data-stu-id="a74a1-273">7</span></span>|
   ||<span data-ttu-id="a74a1-274">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-274">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-275">Total del pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-275">Total the order</span></span>|
   ||<span data-ttu-id="a74a1-276">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-276">AccessibleName</span></span>|<span data-ttu-id="a74a1-277">Total del pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-277">Total order</span></span>|
   |<span data-ttu-id="a74a1-278">Botón</span><span class="sxs-lookup"><span data-stu-id="a74a1-278">Button</span></span>|<span data-ttu-id="a74a1-279">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-279">Name</span></span>|<span data-ttu-id="a74a1-280">cancel</span><span class="sxs-lookup"><span data-stu-id="a74a1-280">cancel</span></span>|
   ||<span data-ttu-id="a74a1-281">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-281">Text</span></span>|<span data-ttu-id="a74a1-282">&Cancelar</span><span class="sxs-lookup"><span data-stu-id="a74a1-282">&Cancel</span></span>|
   ||<span data-ttu-id="a74a1-283">TabIndex</span><span class="sxs-lookup"><span data-stu-id="a74a1-283">TabIndex</span></span>|<span data-ttu-id="a74a1-284">8</span><span class="sxs-lookup"><span data-stu-id="a74a1-284">8</span></span>|
   ||<span data-ttu-id="a74a1-285">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="a74a1-285">AccessibleDescription</span></span>|<span data-ttu-id="a74a1-286">Cancelar el pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-286">Cancel the order</span></span>|
   ||<span data-ttu-id="a74a1-287">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="a74a1-287">AccessibleName</span></span>|<span data-ttu-id="a74a1-288">Cancelar pedido</span><span class="sxs-lookup"><span data-stu-id="a74a1-288">Cancel order</span></span>|
   |<span data-ttu-id="a74a1-289">MainMenu</span><span class="sxs-lookup"><span data-stu-id="a74a1-289">MainMenu</span></span>|<span data-ttu-id="a74a1-290">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-290">Name</span></span>|<span data-ttu-id="a74a1-291">theMainMenu</span><span class="sxs-lookup"><span data-stu-id="a74a1-291">theMainMenu</span></span>|
   |<span data-ttu-id="a74a1-292">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a74a1-292">MenuItem</span></span>|<span data-ttu-id="a74a1-293">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-293">Name</span></span>|<span data-ttu-id="a74a1-294">fileCommands</span><span class="sxs-lookup"><span data-stu-id="a74a1-294">fileCommands</span></span>|
   ||<span data-ttu-id="a74a1-295">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-295">Text</span></span>|<span data-ttu-id="a74a1-296">&Archivo</span><span class="sxs-lookup"><span data-stu-id="a74a1-296">&File</span></span>|
   |<span data-ttu-id="a74a1-297">MenuItem</span><span class="sxs-lookup"><span data-stu-id="a74a1-297">MenuItem</span></span>|<span data-ttu-id="a74a1-298">Name</span><span class="sxs-lookup"><span data-stu-id="a74a1-298">Name</span></span>|<span data-ttu-id="a74a1-299">exitApp</span><span class="sxs-lookup"><span data-stu-id="a74a1-299">exitApp</span></span>|
   ||<span data-ttu-id="a74a1-300">Text</span><span class="sxs-lookup"><span data-stu-id="a74a1-300">Text</span></span>|<span data-ttu-id="a74a1-301">&Salir</span><span class="sxs-lookup"><span data-stu-id="a74a1-301">E&xit</span></span>|

   <span data-ttu-id="a74a1-302">El formulario tendrá un aspecto similar al de la siguiente imagen:</span><span class="sxs-lookup"><span data-stu-id="a74a1-302">Your form will look something like the following image:</span></span>

   ![El formulario de pedido de pizza con un cuadro de texto de nombre y la selección de tamaño y de subpings.](./media/walkthrough-creating-an-accessible-windows-based-application/visual-basic-pizza-order-form.gif)

## <a name="supporting-high-contrast-mode"></a><span data-ttu-id="a74a1-304">Compatibilidad con el modo de contraste alto</span><span class="sxs-lookup"><span data-stu-id="a74a1-304">Supporting High Contrast Mode</span></span>

<span data-ttu-id="a74a1-305">El modo de contraste alto es una configuración de sistema de Windows que mejora la legibilidad mediante el uso de colores de contraste y tamaños de fuente que son beneficiosos para los usuarios con discapacidades visuales.</span><span class="sxs-lookup"><span data-stu-id="a74a1-305">High Contrast mode is a Windows system setting that improves readability by using contrasting colors and font sizes that are beneficial for visually impaired users.</span></span> <span data-ttu-id="a74a1-306">La <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> propiedad se proporciona para determinar si el modo de contraste alto está establecido.</span><span class="sxs-lookup"><span data-stu-id="a74a1-306">The <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> property is provided to determine whether the High Contrast mode is set.</span></span>

<span data-ttu-id="a74a1-307">Si SystemInformation.HighContrast es `true`, la aplicación debe:</span><span class="sxs-lookup"><span data-stu-id="a74a1-307">If SystemInformation.HighContrast is `true`, the application should:</span></span>

- <span data-ttu-id="a74a1-308">Mostrar todos los elementos de interfaz de usuario mediante la combinación de colores del sistema</span><span class="sxs-lookup"><span data-stu-id="a74a1-308">Display all user interface elements using the system color scheme</span></span>

- <span data-ttu-id="a74a1-309">Ofrecer mediante indicaciones visuales o sonoras cualquier información que se ofrezca mediante el color.</span><span class="sxs-lookup"><span data-stu-id="a74a1-309">Convey by visual cues or sound any information that is conveyed through color.</span></span> <span data-ttu-id="a74a1-310">Por ejemplo, si se resaltan determinados elementos de una lista mediante una fuente de color rojo, también se podría aplicar negrita a la fuente para que el usuario pueda ver, sin percibir el color, que los elementos están resaltados.</span><span class="sxs-lookup"><span data-stu-id="a74a1-310">For example, if particular list items are highlighted by using a red font, you could also add bold to the font, so that the user has a non-color cue that the items are highlighted.</span></span>

- <span data-ttu-id="a74a1-311">Omitir las imágenes o tramas detrás del texto</span><span class="sxs-lookup"><span data-stu-id="a74a1-311">Omit any images or patterns behind text</span></span>

<span data-ttu-id="a74a1-312">La aplicación debe comprobar la configuración de <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> cuando se inicia la aplicación y responder al evento de sistema <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="a74a1-312">The application should check the setting of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> when the application starts and respond to the system event <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span></span> <span data-ttu-id="a74a1-313">El evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> se genera siempre que el valor de <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> cambia.</span><span class="sxs-lookup"><span data-stu-id="a74a1-313">The <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event is raised whenever the value of <xref:System.Windows.Forms.SystemInformation.HighContrast%2A> changes.</span></span>

<span data-ttu-id="a74a1-314">En nuestra aplicación, el único elemento que no usa la configuración de color del sistema es `lblCompanyName`.</span><span class="sxs-lookup"><span data-stu-id="a74a1-314">In our application, the only element that is not using the system settings for color is `lblCompanyName`.</span></span> <span data-ttu-id="a74a1-315">La <xref:System.Drawing.SystemColors> clase se usa para cambiar la configuración de color de la etiqueta a los colores del sistema seleccionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a74a1-315">The <xref:System.Drawing.SystemColors> class is used to change the color settings of the label to the user-selected system colors.</span></span>

#### <a name="to-enable-high-contrast-mode-in-an-effective-way"></a><span data-ttu-id="a74a1-316">Para habilitar el modo de contraste alto de forma eficaz</span><span class="sxs-lookup"><span data-stu-id="a74a1-316">To enable High Contrast mode in an effective way</span></span>

1. <span data-ttu-id="a74a1-317">Cree un método para establecer los colores de la etiqueta en los colores del sistema.</span><span class="sxs-lookup"><span data-stu-id="a74a1-317">Create a method to set the colors of the label to the system colors.</span></span>

    ```vb
    Private Sub SetColorScheme()
        If SystemInformation.HighContrast Then
            companyLabel.BackColor = SystemColors.Window
            companyLabel.ForeColor = SystemColors.WindowText
        Else
            companyLabel.BackColor = Color.Blue
            companyLabel.ForeColor = Color.Yellow
        End If
    End Sub
    ```

    ```csharp
    private void SetColorScheme()
    {
        if (SystemInformation.HighContrast)
        {
            companyLabel.BackColor = SystemColors.Window;
            companyLabel.ForeColor = SystemColors.WindowText;
        }
        else
        {
            companyLabel.BackColor = Color.Blue;
            companyLabel.ForeColor = Color.Yellow;
        }
    }
    ```

2. <span data-ttu-id="a74a1-318">Llame al procedimiento `SetColorScheme` en el constructor del formulario (`Public Sub New()` en Visual Basic y `public Form1()` en Visual C#).</span><span class="sxs-lookup"><span data-stu-id="a74a1-318">Call the `SetColorScheme` procedure in the form constructor (`Public Sub New()` in Visual Basic and `public Form1()` in Visual C#).</span></span> <span data-ttu-id="a74a1-319">Para acceder al constructor en Visual Basic, deberá expandir la región denominada **Código generado por el Diseñador de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="a74a1-319">To access the constructor in Visual Basic, you will need to expand the region labeled **Windows Form Designer generated code**.</span></span>

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
    }
    ```

3. <span data-ttu-id="a74a1-320">Cree un procedimiento de evento con la firma apropiada para responder al evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>.</span><span class="sxs-lookup"><span data-stu-id="a74a1-320">Create an event procedure, with the appropriate signature, to respond to the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event.</span></span>

    ```vb
    Protected Sub UserPreferenceChanged(sender As Object, _
    e As Microsoft.Win32.UserPreferenceChangedEventArgs)
        SetColorScheme()
    End Sub
    ```

    ```csharp
    public void UserPreferenceChanged(object sender,
    Microsoft.Win32.UserPreferenceChangedEventArgs e)
    {
        SetColorScheme();
    }
    ```

4. <span data-ttu-id="a74a1-321">Agregue código al constructor del formulario, después de la llamada a `InitializeComponents`, para enlazar el procedimiento de evento al evento del sistema.</span><span class="sxs-lookup"><span data-stu-id="a74a1-321">Add code to the form constructor, after the call to `InitializeComponents`, to hook up the event procedure to the system event.</span></span> <span data-ttu-id="a74a1-322">Este método llama al procedimiento `SetColorScheme`.</span><span class="sxs-lookup"><span data-stu-id="a74a1-322">This method calls the `SetColorScheme` procedure.</span></span>

    ```vb
    Public Sub New()
        MyBase.New()
        InitializeComponent()
        SetColorScheme()
        AddHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
    End Sub
    ```

    ```csharp
    public Form1()
    {
        InitializeComponent();
        SetColorScheme();
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           += new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
    }
    ```

5. <span data-ttu-id="a74a1-323">Agregue código al método <xref:System.Windows.Forms.Control.Dispose%2A> del formulario, antes de llamar al método <xref:System.Windows.Forms.Control.Dispose%2A> de la clase base, para liberar el evento cuando se cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-323">Add code to the form <xref:System.Windows.Forms.Control.Dispose%2A> method, before the call to the <xref:System.Windows.Forms.Control.Dispose%2A> method of the base class, to release the event when the application closes.</span></span> <span data-ttu-id="a74a1-324">Para tener acceso al método <xref:System.Windows.Forms.Control.Dispose%2A> en Visual Basic, deberá expandir la región denominada Código generado por el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a74a1-324">To access the <xref:System.Windows.Forms.Control.Dispose%2A> method in Visual Basic, you will need to expand the region labeled Windows Form Designer generated code.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a74a1-325">El código de evento del sistema ejecuta un subproceso independiente de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="a74a1-325">The system event code runs a thread separate from the main application.</span></span> <span data-ttu-id="a74a1-326">Si no libera el evento, el código que enlazó al evento se ejecutará incluso después de cerrar el programa.</span><span class="sxs-lookup"><span data-stu-id="a74a1-326">If you do not release the event, the code that you hook up to the event will run even after the program is closed.</span></span>

    ```vb
    Protected Overloads Overrides Sub Dispose(ByVal disposing As Boolean)
        If disposing AndAlso components IsNot Nothing Then
            components.Dispose()
        End If
        RemoveHandler Microsoft.Win32.SystemEvents.UserPreferenceChanged, _
           AddressOf Me.UserPreferenceChanged
        MyBase.Dispose(disposing)
    End Sub
    ```

    ```csharp
    protected override void Dispose(bool disposing)
    {
        if(disposing && components != null)
        {
            components.Dispose();
        }
        Microsoft.Win32.SystemEvents.UserPreferenceChanged
           -= new Microsoft.Win32.UserPreferenceChangedEventHandler(
           this.UserPreferenceChanged);
        base.Dispose( disposing );
    }
    ```

6. <span data-ttu-id="a74a1-327">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-327">Press F5 to run the application.</span></span>

## <a name="conveying-important-information-by-means-other-than-sound"></a><span data-ttu-id="a74a1-328">Ofrecer información importante por medios diferentes del sonido</span><span class="sxs-lookup"><span data-stu-id="a74a1-328">Conveying Important Information by Means Other Than Sound</span></span>

<span data-ttu-id="a74a1-329">En esta aplicación no se muestra ninguna información solo mediante sonido.</span><span class="sxs-lookup"><span data-stu-id="a74a1-329">In this application, no information is conveyed by sound alone.</span></span> <span data-ttu-id="a74a1-330">Si usa sonido en la aplicación, también debe proporcionar la información de algún otro modo.</span><span class="sxs-lookup"><span data-stu-id="a74a1-330">If you use sound in your application, then you should supply the information by some other means as well.</span></span>

#### <a name="to-supply-information-by-some-other-means-than-sound"></a><span data-ttu-id="a74a1-331">Para proporcionar información por otros medios distintos del sonido</span><span class="sxs-lookup"><span data-stu-id="a74a1-331">To supply information by some other means than sound</span></span>

1. <span data-ttu-id="a74a1-332">Haga parpadear la barra de título flash con la función de API de Windows FlashWindow.</span><span class="sxs-lookup"><span data-stu-id="a74a1-332">Make the title bar flash by using the Windows API function FlashWindow.</span></span> <span data-ttu-id="a74a1-333">Para obtener un ejemplo de cómo llamar a las funciones de la [API de Windows, vea Tutorial: Llamando a las](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)API de Windows.</span><span class="sxs-lookup"><span data-stu-id="a74a1-333">For an example of how to call Windows API functions, see [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="a74a1-334">El usuario puede tener el servicio SoundSentry de Windows habilitado, que también hace que la ventana parpadee cuando se reproducen los sonidos del sistema a través de los altavoces integrados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a74a1-334">The user may have the Windows SoundSentry service enabled, which will also cause the window to flash when the system sounds are played through the computer's built-in speaker.</span></span>

2. <span data-ttu-id="a74a1-335">Muestre la información importante en una ventana no modal para que el usuario pueda responder a ella.</span><span class="sxs-lookup"><span data-stu-id="a74a1-335">Display the important information in a non-modal window so that the user may respond to it.</span></span>

3. <span data-ttu-id="a74a1-336">Muestre un cuadro de mensaje que adquiera el foco del teclado.</span><span class="sxs-lookup"><span data-stu-id="a74a1-336">Display a message box that acquires the keyboard focus.</span></span> <span data-ttu-id="a74a1-337">Evite usar este método cuando el usuario esté escribiendo.</span><span class="sxs-lookup"><span data-stu-id="a74a1-337">Avoid this method when the user may be typing.</span></span>

4. <span data-ttu-id="a74a1-338">Muestre un indicador de estado en el área de notificación de estado de la barra de tareas.</span><span class="sxs-lookup"><span data-stu-id="a74a1-338">Display a status indicator in the status notification area of the taskbar.</span></span> <span data-ttu-id="a74a1-339">Para ver detalles, consulte [Cómo: Agregar iconos de aplicación a la barra de tareas con el componente NotifyIcon de Windows Forms](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="a74a1-339">For details, see [Adding Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>

## <a name="testing-the-application"></a><span data-ttu-id="a74a1-340">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a74a1-340">Testing the Application</span></span>

<span data-ttu-id="a74a1-341">Antes de implementar la aplicación, pruebe las características de accesibilidad que se han implementado.</span><span class="sxs-lookup"><span data-stu-id="a74a1-341">Before deploying the application, you should test the accessibility features that you have implemented.</span></span>

#### <a name="to-test-accessibility-features"></a><span data-ttu-id="a74a1-342">Para probar las características de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="a74a1-342">To test accessibility features</span></span>

1. <span data-ttu-id="a74a1-343">Para probar el acceso mediante teclado, desconecte el mouse y desplácese por cada característica de la interfaz de usuario usando solo el teclado.</span><span class="sxs-lookup"><span data-stu-id="a74a1-343">To test keyboard access, unplug the mouse and navigate the user interface for each feature using only the keyboard.</span></span> <span data-ttu-id="a74a1-344">Asegúrese de que todas las tareas pueden realizarse utilizando únicamente el teclado.</span><span class="sxs-lookup"><span data-stu-id="a74a1-344">Ensure that all tasks may be performed using the keyboard only.</span></span>

2. <span data-ttu-id="a74a1-345">Para probar la compatibilidad de contraste alto, elija el icono de opciones de accesibilidad en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a74a1-345">To test support of High Contrast, choose the Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="a74a1-346">Haga clic en la ficha Pantalla y seleccione la casilla Usar contraste alto.</span><span class="sxs-lookup"><span data-stu-id="a74a1-346">Click the Display tab and select the Use High Contrast check box.</span></span> <span data-ttu-id="a74a1-347">Desplácese por todos los elementos de la interfaz de usuario para asegurarse de que se reflejan los cambios de color y fuente.</span><span class="sxs-lookup"><span data-stu-id="a74a1-347">Navigate through all user interface elements to ensure that the color and font changes are reflected.</span></span> <span data-ttu-id="a74a1-348">Asegúrese también de que se omiten las imágenes o las tramas que se representan detrás del texto.</span><span class="sxs-lookup"><span data-stu-id="a74a1-348">Also, ensure that images or patterns drawn behind text are omitted.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a74a1-349">Windows NT 4 no tiene un icono de opciones de accesibilidad en el Panel de control.</span><span class="sxs-lookup"><span data-stu-id="a74a1-349">Windows NT 4 does not have an Accessibility Options icon in Control Panel.</span></span> <span data-ttu-id="a74a1-350">Por lo tanto, este procedimiento para cambiar el valor SystemInformation.HighContrast no funciona en Windows NT 4.</span><span class="sxs-lookup"><span data-stu-id="a74a1-350">Thus, this procedure for changing the SystemInformation.HighContrast setting does not work in Windows NT 4.</span></span>

3. <span data-ttu-id="a74a1-351">Hay otras herramientas disponibles para probar la accesibilidad de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a74a1-351">Other tools are readily available for testing the accessibility of an application.</span></span>

4. <span data-ttu-id="a74a1-352">Para probar la exposición del foco de teclado, ejecute la Lupa.</span><span class="sxs-lookup"><span data-stu-id="a74a1-352">To test exposing the keyboard focus, run Magnifier.</span></span> <span data-ttu-id="a74a1-353">(Para abrirla, haga clic en **Inicio**, elija **Programas**, **Accesorios** y **Accesibilidad**, y haga clic en **Lupa**).</span><span class="sxs-lookup"><span data-stu-id="a74a1-353">(To open it, click the **Start** menu, point to **Programs**, point to **Accessories**, point to **Accessibility**, and then click **Magnifier**).</span></span> <span data-ttu-id="a74a1-354">Desplácese por la interfaz de usuario usando tanto la tabulación de teclado como el mouse.</span><span class="sxs-lookup"><span data-stu-id="a74a1-354">Navigate the user interface using both keyboard tabbing and the mouse.</span></span> <span data-ttu-id="a74a1-355">Asegúrese de que la **Lupa** siga correctamente todos los desplazamientos.</span><span class="sxs-lookup"><span data-stu-id="a74a1-355">Ensure that all navigation is tracked properly in **Magnifier**.</span></span>

5. <span data-ttu-id="a74a1-356">Para probar la exposición de los elementos de pantalla, ejecute Inspeccionar y use el mouse y la tecla TAB para desplazarse a cada elemento.</span><span class="sxs-lookup"><span data-stu-id="a74a1-356">To test exposing screen elements, run Inspect, and use both the mouse and the TAB key to reach each element.</span></span> <span data-ttu-id="a74a1-357">Asegúrese de que la información contenida en los campos de nombre, estado, rol, ubicación y valor de la ventana Inspeccionar es significativa para el usuario en relación a cada objeto de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a74a1-357">Ensure that the information presented in the Name, State, Role, Location, and Value fields of the Inspect window is meaningful to the user for each object in the UI.</span></span>
