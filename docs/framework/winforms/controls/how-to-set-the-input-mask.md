---
title: Procedimiento para establecer la máscara de entrada
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 06dee48765653ac7a659246cc3dfe865c795ca21
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949147"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="1e4b1-102">Procedimiento para establecer la máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="1e4b1-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="1e4b1-103">El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="1e4b1-104">Al establecer la propiedad Mask, puede especificar la entrada de usuario permitida sin escribir ninguna lógica de validación personalizada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="1e4b1-105">Para obtener más información, vea la sección Comentarios de <xref:System.Windows.Forms.MaskedTextBox> la clase.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="1e4b1-106">Establecimiento manual de la propiedad Mask</span><span class="sxs-lookup"><span data-stu-id="1e4b1-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="1e4b1-107">Si está familiarizado con los caracteres que admite la propiedad Mask, puede especificarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="1e4b1-108">Para obtener un resumen de los caracteres que admite la propiedad Mask, vea la sección Comentarios de <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="1e4b1-109">Para establecer la propiedad Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="1e4b1-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="1e4b1-110">En la vista **diseño** , seleccione <xref:System.Windows.Forms.MaskedTextBox>un.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="1e4b1-111">En la ventana **propiedades** , busque la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="1e4b1-112">Escriba la máscara que desee.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-112">Type the mask that you want.</span></span> <span data-ttu-id="1e4b1-113">Por ejemplo, escriba `###`.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="1e4b1-114">Usar el cuadro de diálogo máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="1e4b1-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="1e4b1-115">El cuadro de diálogo máscara de entrada proporciona algunas máscaras de entrada predefinidas.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="1e4b1-116">También puede cambiar las máscaras predefinidas o escribir su propia máscara manualmente.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="1e4b1-117">Para abrir el cuadro de diálogo máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="1e4b1-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="1e4b1-118">En la vista **diseño** , seleccione <xref:System.Windows.Forms.MaskedTextBox>un.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="1e4b1-119">Haga clic en la etiqueta inteligente para abrir el panel de **tareas de MaskedTextBox** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="1e4b1-120">Haga clic en **establecer máscara**.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="1e4b1-121">\- o -</span><span class="sxs-lookup"><span data-stu-id="1e4b1-121">\- or -</span></span>  
  
    1. <span data-ttu-id="1e4b1-122">En la ventana **propiedades** , seleccione la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="1e4b1-123">Haga clic en el botón de puntos suspensivos en la columna valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="1e4b1-124">Aparece el cuadro de diálogo **máscara de entrada** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-124">The **Input Mask** dialog box appears.</span></span>  
  
### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="1e4b1-125">Para usar el cuadro de diálogo máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="1e4b1-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="1e4b1-126">Opta Haga clic en una de las máscaras predefinidas de la lista.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="1e4b1-127">Opta Edite la máscara predefinida en el cuadro **máscara** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="1e4b1-128">Opta Escriba una nueva máscara en el cuadro **máscara** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="1e4b1-129">Es decir, no tiene que utilizar una de las máscaras predefinidas.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1e4b1-130">El cuadro vista previa muestra los caracteres que el usuario ve en <xref:System.Windows.Forms.MaskedTextBox>el.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="1e4b1-131">Estos caracteres son una guía para ayudar al usuario a escribir los datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="1e4b1-132">Active o desactive la casilla **usar ValidatingType** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="1e4b1-133">La casilla **usar ValidatingType** especifica si se utiliza un tipo de datos para comprobar la entrada de datos por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="1e4b1-134">Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="1e4b1-135">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e4b1-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="1e4b1-136">La máscara se especifica en la propiedad **Mask** de la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="1e4b1-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4b1-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e4b1-137">See also</span></span>

- [<span data-ttu-id="1e4b1-138">Tutorial: Trabajar con el control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="1e4b1-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
