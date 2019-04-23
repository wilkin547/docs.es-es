---
title: Información general sobre el componente ColorDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 284d42218fb4fbce873325b1e45c883d51eefab8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222359"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="69459-102">Información general sobre el componente ColorDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="69459-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="69459-103">Los formularios de Windows <xref:System.Windows.Forms.ColorDialog> componente es un cuadro de diálogo preconfigurado que permite al usuario seleccionar un color de una paleta y agregar colores personalizados a la paleta.</span><span class="sxs-lookup"><span data-stu-id="69459-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="69459-104">Es el mismo cuadro de diálogo que se ve en otras aplicaciones basadas en Windows para seleccionar colores.</span><span class="sxs-lookup"><span data-stu-id="69459-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="69459-105">Utilícelo en la aplicación basada en Windows como una solución sencilla, en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="69459-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="69459-106">Se devuelve el color seleccionado en el cuadro de diálogo en el <xref:System.Windows.Forms.ColorDialog.Color%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="69459-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="69459-107">Si el <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> propiedad está establecida en `false`, el botón "Definir colores personalizados" está deshabilitado y el usuario está restringido a los colores predefinidos en la paleta.</span><span class="sxs-lookup"><span data-stu-id="69459-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="69459-108">Si el <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> propiedad está establecida en `true`, el usuario no puede seleccionar colores interpolados.</span><span class="sxs-lookup"><span data-stu-id="69459-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="69459-109">Para mostrar el cuadro de diálogo, debe llamar a su <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="69459-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69459-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="69459-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="69459-111">ColorDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="69459-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="69459-112">Controles y componentes de cuadros de diálogo</span><span class="sxs-lookup"><span data-stu-id="69459-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="69459-113">Cómo: Cambiar la apariencia del componente ColorDialog de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69459-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
