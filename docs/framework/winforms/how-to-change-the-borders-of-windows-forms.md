---
title: Cambiar los bordes del formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739563"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="fa4c9-102">Cómo: Cambiar los bordes de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa4c9-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="fa4c9-103">Puede elegir varios estilos de borde para determinar la apariencia y el comportamiento de sus Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="fa4c9-104">Puede cambiar la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> para controlar el comportamiento de cambio de tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="fa4c9-105">Además, establecer el <xref:System.Windows.Forms.Form.FormBorderStyle%2A> afecta a cómo se muestra la barra de título y qué botones pueden aparecer en ella.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="fa4c9-106">Para más información, consulte <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="fa4c9-107">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="fa4c9-108">Vea también [Cómo: cambiar los bordes de Windows Forms mediante el diseñador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fa4c9-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="fa4c9-109">Para establecer el estilo de borde de Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="fa4c9-109">To set the border style of Windows Forms programmatically</span></span>  
  
- <span data-ttu-id="fa4c9-110">Establezca la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> en el estilo que desee.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="fa4c9-111">En el ejemplo de código siguiente se establece el estilo de borde del formulario `DlgBx1` en <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="fa4c9-112">Consulte también [Cómo: crear cuadros de diálogo en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="fa4c9-112">Also see [How to: Create Dialog Boxes at Design Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).</span></span>  
  
     <span data-ttu-id="fa4c9-113">Además, si ha elegido un estilo de borde para el formulario que proporciona botones opcionales para **minimizar** y **maximizar** , puede especificar si desea que uno o ambos botones sean funcionales.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="fa4c9-114">Estos botones son útiles si desea controlar estrechamente la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="fa4c9-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="fa4c9-115">Los botones **minimizar** y **maximizar** están habilitados de forma predeterminada y su funcionalidad se manipula a través de la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="fa4c9-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4c9-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa4c9-116">See also</span></span>

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [<span data-ttu-id="fa4c9-117">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fa4c9-117">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
