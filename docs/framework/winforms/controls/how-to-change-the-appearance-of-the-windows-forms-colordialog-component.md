---
title: Filtrar para cambiar la apariencia del componente ColorDialog de formularios Windows Forms
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
ms.openlocfilehash: d2bb9e06d9d84a9b61c67510e9c012066f69d55e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329237"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="d325f-102">Filtrar para cambiar la apariencia del componente ColorDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d325f-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="d325f-103">Puede configurar la apariencia de los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente con un número de sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="d325f-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="d325f-104">El cuadro de diálogo tiene dos secciones: una que muestra los colores básicos y otra que permite al usuario definir colores personalizados.</span><span class="sxs-lookup"><span data-stu-id="d325f-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="d325f-105">La mayoría de las propiedades restringen los colores que el usuario puede seleccionar desde el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d325f-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="d325f-106">Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `true`, el usuario puede definir colores personalizados.</span><span class="sxs-lookup"><span data-stu-id="d325f-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="d325f-107">El <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> propiedad es `true` si se expande el cuadro de diálogo para definir colores personalizados; en caso contrario, el usuario debe hacer clic en un botón "Definir colores personalizados".</span><span class="sxs-lookup"><span data-stu-id="d325f-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="d325f-108">Cuando el <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> propiedad está establecida en `true`, el cuadro de diálogo muestra todos los colores disponibles en el conjunto de colores básicos.</span><span class="sxs-lookup"><span data-stu-id="d325f-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="d325f-109">Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados; están disponibles para seleccionar sólo colores sólidos.</span><span class="sxs-lookup"><span data-stu-id="d325f-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="d325f-110">Si el <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> propiedad está establecida en `true`, aparece un botón de ayuda en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d325f-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="d325f-111">Cuando el usuario hace clic en el botón Ayuda, el <xref:System.Windows.Forms.ColorDialog> del componente <xref:System.Windows.Forms.CommonDialog.HelpRequest> provoca el evento.</span><span class="sxs-lookup"><span data-stu-id="d325f-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="d325f-112">Para configurar la apariencia del cuadro de diálogo color</span><span class="sxs-lookup"><span data-stu-id="d325f-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="d325f-113">Establecer el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, y <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> propiedades en los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="d325f-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d325f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d325f-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="d325f-115">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d325f-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="d325f-116">Información general sobre el componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="d325f-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
