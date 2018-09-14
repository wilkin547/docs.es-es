---
title: 'Cómo: Cambiar los bordes de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: e04234b4f2f18738567c3f9846d8ae0c94780fcb
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615916"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="c4082-102">Cómo: Cambiar los bordes de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4082-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="c4082-103">Puede elegir varios estilos de borde para determinar la apariencia y el comportamiento de sus Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c4082-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="c4082-104">Puede cambiar la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> para controlar el comportamiento de cambio de tamaño del formulario.</span><span class="sxs-lookup"><span data-stu-id="c4082-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="c4082-105">Además, establecer el <xref:System.Windows.Forms.Form.FormBorderStyle%2A> afecta a cómo se muestra la barra de título y qué botones pueden aparecer en ella.</span><span class="sxs-lookup"><span data-stu-id="c4082-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="c4082-106">Para obtener más información, consulta <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="c4082-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="c4082-107">Visual Studio es altamente compatible con esta tarea.</span><span class="sxs-lookup"><span data-stu-id="c4082-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="c4082-108">Vea también [Cómo: cambiar los bordes de formularios de Windows mediante el diseñador](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c4082-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="c4082-109">Para establecer el estilo de borde de Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="c4082-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="c4082-110">Establezca la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> en el estilo que desee.</span><span class="sxs-lookup"><span data-stu-id="c4082-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="c4082-111">El ejemplo de código siguiente establece el estilo de borde del formulario `DlgBx1` a <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="c4082-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
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
  
     <span data-ttu-id="c4082-112">Consulte también [Cómo: crear cuadros de diálogo en tiempo de diseño](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c4082-112">Also see [How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="c4082-113">Además, si ha elegido un estilo de borde para el formulario que proporciona opcional **minimizar** y **maximizar** botones, puede especificar si desea que uno o ambos de estos botones sean funcionales.</span><span class="sxs-lookup"><span data-stu-id="c4082-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="c4082-114">Estos botones son útiles si desea controlar estrechamente la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="c4082-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="c4082-115">El **minimizar** y **maximizar** botones están habilitados de forma predeterminada, y su funcionalidad se manipula a través de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="c4082-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4082-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4082-116">See Also</span></span>  
 <xref:System.Windows.Forms.FormBorderStyle>  
 <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>  
 [<span data-ttu-id="c4082-117">Introducción a los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4082-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
