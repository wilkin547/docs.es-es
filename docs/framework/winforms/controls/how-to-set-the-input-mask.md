---
title: Filtrar Establecer la máscara de entrada
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 53bb8d0e301f83c25ab292b1cb6324dd5f21f100
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702365"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="f6434-102">Procedimiento Establecer la máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="f6434-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="f6434-103">El control de cuadro de texto enmascarado es un control de cuadro de texto mejorado que admite una sintaxis declarativa para aceptar o rechazar la intervención del usuario.</span><span class="sxs-lookup"><span data-stu-id="f6434-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="f6434-104">Al establecer la propiedad Mask, puede especificar la entrada del usuario permitido sin escribir ninguna lógica de validación personalizada en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f6434-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="f6434-105">Para obtener más información, vea la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox> clase.</span><span class="sxs-lookup"><span data-stu-id="f6434-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="f6434-106">Establecer la propiedad Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="f6434-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="f6434-107">Si está familiarizado con los caracteres que la propiedad Mask admite, puede escribirla manualmente.</span><span class="sxs-lookup"><span data-stu-id="f6434-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="f6434-108">Para obtener un resumen de los caracteres compatibles con la propiedad de máscara, consulte la sección Comentarios de la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f6434-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="f6434-109">Para establecer la propiedad Mask manualmente</span><span class="sxs-lookup"><span data-stu-id="f6434-109">To set the Mask property manually</span></span>  
  
1.  <span data-ttu-id="f6434-110">En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f6434-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2.  <span data-ttu-id="f6434-111">En el **propiedades** ventana, busque la <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f6434-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3.  <span data-ttu-id="f6434-112">Escriba la máscara que desee.</span><span class="sxs-lookup"><span data-stu-id="f6434-112">Type the mask that you want.</span></span> <span data-ttu-id="f6434-113">Por ejemplo, escriba `###`.</span><span class="sxs-lookup"><span data-stu-id="f6434-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="f6434-114">Mediante el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="f6434-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="f6434-115">El cuadro de diálogo de máscara de entrada proporciona algunas máscaras de entrada predefinidos.</span><span class="sxs-lookup"><span data-stu-id="f6434-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="f6434-116">También puede cambiar las máscaras predefinidas o escribir manualmente su propia máscara.</span><span class="sxs-lookup"><span data-stu-id="f6434-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="f6434-117">Para abrir el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="f6434-117">To open the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="f6434-118">En **diseño** visualizarla, seleccione un <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f6434-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="f6434-119">Haga clic en la etiqueta inteligente para abrir el **MaskedTextBox tareas** panel.</span><span class="sxs-lookup"><span data-stu-id="f6434-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="f6434-120">Haga clic en **establecer máscara**.</span><span class="sxs-lookup"><span data-stu-id="f6434-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="f6434-121">\- o -</span><span class="sxs-lookup"><span data-stu-id="f6434-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="f6434-122">En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f6434-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="f6434-123">Haga clic en el botón de puntos suspensivos en la columna de valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f6434-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="f6434-124">El **máscara de entrada** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f6434-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="f6434-125">Para usar el cuadro de diálogo de máscara de entrada</span><span class="sxs-lookup"><span data-stu-id="f6434-125">To use the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="f6434-126">(Opcional) Haga clic en una de las máscaras predefinidas en la lista.</span><span class="sxs-lookup"><span data-stu-id="f6434-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2.  <span data-ttu-id="f6434-127">(Opcional) Modifique la máscara predefinida en el **máscara** cuadro.</span><span class="sxs-lookup"><span data-stu-id="f6434-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3.  <span data-ttu-id="f6434-128">(Opcional) Escriba una máscara nuevo en el **máscara** cuadro.</span><span class="sxs-lookup"><span data-stu-id="f6434-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="f6434-129">Es decir, no es necesario utilizar una de las máscaras predefinidas.</span><span class="sxs-lookup"><span data-stu-id="f6434-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f6434-130">El cuadro de vista previa muestra los caracteres que el usuario ve en el <xref:System.Windows.Forms.MaskedTextBox>.</span><span class="sxs-lookup"><span data-stu-id="f6434-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="f6434-131">Estos caracteres son una guía para ayudar al usuario escribir los datos correctamente.</span><span class="sxs-lookup"><span data-stu-id="f6434-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4.  <span data-ttu-id="f6434-132">Active o desactive el **utilizar ValidatingType** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f6434-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="f6434-133">El **utilizar ValidatingType** casilla especifica si un tipo de datos se usa para comprobar la entrada de datos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f6434-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="f6434-134">Para obtener más información, vea la propiedad <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A>.</span><span class="sxs-lookup"><span data-stu-id="f6434-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5.  <span data-ttu-id="f6434-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6434-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="f6434-136">La máscara se especifica en el **máscara** propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="f6434-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6434-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6434-137">See also</span></span>
- [<span data-ttu-id="f6434-138">Tutorial: Trabajar con el Control MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="f6434-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
