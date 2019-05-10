---
title: Procedimiento para establecer la máscara de entrada
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: dd156f9e5bf6519363f66ca61687f1e9f2bfc6ab
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630427"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="7f666-102">Procedimiento para establecer la máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="7f666-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="7f666-103">El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="7f666-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="7f666-104">Al establecer la propiedad Mask, puede especificar la entrada del usuario permitido sin escribir ninguna lógica de validación personalizada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f666-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="7f666-105">Para obtener más información, vea la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox> clase.</span><span class="sxs-lookup"><span data-stu-id="7f666-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="7f666-106">Establecer la propiedad Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="7f666-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="7f666-107">Si está familiarizado con los caracteres que la propiedad Mask admite, puede escribirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="7f666-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="7f666-108">Para obtener un resumen de los caracteres compatibles con la propiedad de máscara, consulte la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f666-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="7f666-109">Para establecer la propiedad Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="7f666-109">To set the Mask property manually</span></span>  
  
1. <span data-ttu-id="7f666-110">En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7f666-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2. <span data-ttu-id="7f666-111">En el **propiedades** ventana, busque la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f666-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3. <span data-ttu-id="7f666-112">Escriba la máscara que desee.</span><span class="sxs-lookup"><span data-stu-id="7f666-112">Type the mask that you want.</span></span> <span data-ttu-id="7f666-113">Por ejemplo, escriba `###`.</span><span class="sxs-lookup"><span data-stu-id="7f666-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="7f666-114">Mediante el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="7f666-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="7f666-115">El cuadro de diálogo de máscara de entrada proporciona algunas máscaras de entrada predefinidos.</span><span class="sxs-lookup"><span data-stu-id="7f666-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="7f666-116">También puede cambiar las máscaras predefinidas o escribir manualmente su propia máscara.</span><span class="sxs-lookup"><span data-stu-id="7f666-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="7f666-117">Para abrir el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="7f666-117">To open the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="7f666-118">En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7f666-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1. <span data-ttu-id="7f666-119">Haga clic en la etiqueta inteligente para abrir el **MaskedTextBox tareas** panel.</span><span class="sxs-lookup"><span data-stu-id="7f666-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2. <span data-ttu-id="7f666-120">Haga clic en **establecer máscara**.</span><span class="sxs-lookup"><span data-stu-id="7f666-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="7f666-121">\- o -</span><span class="sxs-lookup"><span data-stu-id="7f666-121">\- or -</span></span>  
  
    1. <span data-ttu-id="7f666-122">En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f666-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2. <span data-ttu-id="7f666-123">Haga clic en el botón de puntos suspensivos en la columna de valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7f666-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="7f666-124">El **máscara de entrada** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7f666-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="7f666-125">Para usar el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="7f666-125">To use the Input Mask dialog box</span></span>  
  
1. <span data-ttu-id="7f666-126">(Opcional) Haga clic en una de las máscaras predefinidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="7f666-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2. <span data-ttu-id="7f666-127">(Opcional) Modifique la máscara predefinida en el **máscara** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7f666-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3. <span data-ttu-id="7f666-128">(Opcional) Escriba una máscara nuevo en el **máscara** cuadro.</span><span class="sxs-lookup"><span data-stu-id="7f666-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="7f666-129">Es decir, no es necesario utilizar una de las máscaras predefinidas.</span><span class="sxs-lookup"><span data-stu-id="7f666-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7f666-130">El cuadro de vista previa muestra los caracteres que el usuario ve en el <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="7f666-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="7f666-131">Estos caracteres son una guía para ayudar al usuario escribir los datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="7f666-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4. <span data-ttu-id="7f666-132">Active o desactive el **utilizar ValidatingType** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="7f666-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="7f666-133">El **utilizar ValidatingType** casilla especifica si un tipo de datos se usa para comprobar la entrada de datos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7f666-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="7f666-134">Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="7f666-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5. <span data-ttu-id="7f666-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7f666-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="7f666-136">La máscara se especifica en el **máscara** propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="7f666-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f666-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f666-137">See also</span></span>

- [<span data-ttu-id="7f666-138">Tutorial: Trabajar con el Control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="7f666-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
