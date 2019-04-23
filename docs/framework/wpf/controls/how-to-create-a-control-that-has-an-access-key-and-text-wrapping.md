---
title: Procedimiento Crear un control que tenga tecla de acceso y ajuste de texto
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 48e439719afa2426b5d8f822c621080cdc32514e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174049"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="336c6-102">Procedimiento Crear un control que tenga tecla de acceso y ajuste de texto</span><span class="sxs-lookup"><span data-stu-id="336c6-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>
<span data-ttu-id="336c6-103">En este ejemplo se explica cómo crear un control que tenga una clave de acceso y que admita el ajuste de texto.</span><span class="sxs-lookup"><span data-stu-id="336c6-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="336c6-104">El ejemplo se usa un <xref:System.Windows.Controls.Label> control para ilustrar estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="336c6-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="336c6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="336c6-105">Example</span></span>  
 <span data-ttu-id="336c6-106">**Agregar el ajuste de texto a la etiqueta**</span><span class="sxs-lookup"><span data-stu-id="336c6-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="336c6-107">El <xref:System.Windows.Controls.Label> control no admite el ajuste de texto.</span><span class="sxs-lookup"><span data-stu-id="336c6-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="336c6-108">Si necesita una etiqueta que ajuste el texto en varias líneas, puede anidar otro elemento que sí admita el ajuste de texto y colocarlo dentro de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="336c6-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="336c6-109">El ejemplo siguiente muestra cómo usar un <xref:System.Windows.Controls.TextBlock> para crear una etiqueta que contiene varias líneas de texto.</span><span class="sxs-lookup"><span data-stu-id="336c6-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="336c6-110">**Agregar una tecla de acceso y el ajuste de texto a la etiqueta**</span><span class="sxs-lookup"><span data-stu-id="336c6-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="336c6-111">Si necesita un <xref:System.Windows.Controls.Label> que tiene una clave de acceso (tecla de acceso), use el <xref:System.Windows.Controls.AccessText> elemento que está dentro de la <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="336c6-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="336c6-112">Los controles como <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, y <xref:System.Windows.Controls.GroupBox> dispone de plantillas de control de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="336c6-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="336c6-113">Estas plantillas contienen un <xref:System.Windows.Controls.ContentPresenter>.</span><span class="sxs-lookup"><span data-stu-id="336c6-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="336c6-114">Una de las propiedades que se pueden establecer en el <xref:System.Windows.Controls.ContentPresenter> es <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>= "true", que puede usar para especificar una clave de acceso para el control.</span><span class="sxs-lookup"><span data-stu-id="336c6-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="336c6-115">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Label> que tiene una clave de acceso y admite el ajuste de texto.</span><span class="sxs-lookup"><span data-stu-id="336c6-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="336c6-116">Para habilitar el ajuste de texto, el ejemplo establece la <xref:System.Windows.Controls.AccessText.TextWrapping%2A> propiedad y se usa un carácter de subrayado de caracteres para especificar la clave de acceso.</span><span class="sxs-lookup"><span data-stu-id="336c6-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="336c6-117">(El carácter que sigue inmediatamente al carácter de subrayado es la tecla de acceso).</span><span class="sxs-lookup"><span data-stu-id="336c6-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="336c6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="336c6-118">See also</span></span>

- <span data-ttu-id="336c6-119">[Cómo: Establezca la propiedad de destino de una etiqueta](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="336c6-119">[How to: Set the Target Property of a Label](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span></span>
