---
title: Cambiar la apariencia del componente ColorDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746632"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="9e4e6-102">Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9e4e6-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="9e4e6-103">Puede configurar la apariencia del componente de <xref:System.Windows.Forms.ColorDialog> de Windows Forms con una serie de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="9e4e6-104">El cuadro de diálogo tiene dos secciones: una que muestra los colores básicos y otra que permite al usuario definir colores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="9e4e6-105">La mayoría de las propiedades restringen qué colores puede seleccionar el usuario en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="9e4e6-106">Si la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> está establecida en `true`, el usuario puede definir colores personalizados.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="9e4e6-107">La propiedad <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> se `true` si se expande el cuadro de diálogo para definir colores personalizados. de lo contrario, el usuario debe hacer clic en el botón "definir colores personalizados".</span><span class="sxs-lookup"><span data-stu-id="9e4e6-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="9e4e6-108">Cuando la propiedad <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> está establecida en `true`, el cuadro de diálogo muestra todos los colores disponibles en el conjunto de colores básicos.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="9e4e6-109">Si la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> está establecida en `true`, el usuario no puede seleccionar colores propuestos; solo están disponibles para seleccionar los colores sólidos.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="9e4e6-110">Si la propiedad <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> está establecida en `true`, aparece un botón ayuda en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="9e4e6-111">Cuando el usuario hace clic en el botón ayuda, se genera el evento <xref:System.Windows.Forms.CommonDialog.HelpRequest> del componente de <xref:System.Windows.Forms.ColorDialog>.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="9e4e6-112">Para configurar la apariencia del cuadro de diálogo color</span><span class="sxs-lookup"><span data-stu-id="9e4e6-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="9e4e6-113">Establezca las propiedades <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>y <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> en los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="9e4e6-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9e4e6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e4e6-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="9e4e6-115">ColorDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="9e4e6-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="9e4e6-116">Información general del componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="9e4e6-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
