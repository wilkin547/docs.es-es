---
title: Información general sobre el componente ColorDialog
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 48d9d5072335908f85e65933dadafb1b69f28528
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736968"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="efe38-102">Información general sobre el componente ColorDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="efe38-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="efe38-103">El componente de <xref:System.Windows.Forms.ColorDialog> de Windows Forms es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregar colores personalizados a la paleta.</span><span class="sxs-lookup"><span data-stu-id="efe38-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="efe38-104">Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores.</span><span class="sxs-lookup"><span data-stu-id="efe38-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="efe38-105">Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="efe38-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="efe38-106">El color seleccionado en el cuadro de diálogo se devuelve en la propiedad <xref:System.Windows.Forms.ColorDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="efe38-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="efe38-107">Si la propiedad <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> está establecida en `false`, el botón "definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos de la paleta.</span><span class="sxs-lookup"><span data-stu-id="efe38-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="efe38-108">Si la propiedad <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> está establecida en `true`, el usuario no puede seleccionar colores propuestos.</span><span class="sxs-lookup"><span data-stu-id="efe38-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="efe38-109">Para mostrar el cuadro de diálogo, debe llamar a su método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="efe38-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe38-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="efe38-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="efe38-111">ColorDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="efe38-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="efe38-112">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="efe38-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="efe38-113">Cómo: Cambiar la apariencia del componente ColorDialog de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="efe38-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
