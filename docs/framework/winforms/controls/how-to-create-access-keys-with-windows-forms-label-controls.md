---
title: "Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ad6cd99a6399adea2e69cbf844b9f134d2e592e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="2245a-102">Cómo: Crear teclas de acceso con controles Label de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2245a-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="2245a-103">Formularios Windows Forms <xref:System.Windows.Forms.Label> controles pueden utilizarse para definir teclas de acceso para otros controles.</span><span class="sxs-lookup"><span data-stu-id="2245a-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="2245a-104">Al definir una tecla de acceso en un control de etiqueta, el usuario puede presionar la tecla ALT y el carácter designado para mover el foco al control que sigue en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="2245a-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="2245a-105">Dado que las etiquetas no pueden recibir el foco, el foco automáticamente se desplaza al siguiente control en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="2245a-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="2245a-106">Utilice esta técnica para asignar teclas de acceso a cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.</span><span class="sxs-lookup"><span data-stu-id="2245a-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="2245a-107">Para asignar una tecla de acceso a un control con una etiqueta</span><span class="sxs-lookup"><span data-stu-id="2245a-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="2245a-108">Dibuje primero la etiqueta y, a continuación, dibuje el otro control.</span><span class="sxs-lookup"><span data-stu-id="2245a-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="2245a-109">O bien</span><span class="sxs-lookup"><span data-stu-id="2245a-109">-or-</span></span>  
  
     <span data-ttu-id="2245a-110">Dibuje los controles en cualquier orden y establezca el <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de la etiqueta hasta uno menos que el otro control.</span><span class="sxs-lookup"><span data-stu-id="2245a-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="2245a-111">Establezca la etiqueta <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="2245a-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="2245a-112">Utilice una y comercial (&) en la etiqueta <xref:System.Windows.Forms.Label.Text%2A> propiedad para asignar la tecla de acceso para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="2245a-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="2245a-113">Para obtener más información, consulte [crear teclas de acceso para controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="2245a-113">For more information, see [Creating Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2245a-114">Puede que desee mostrar una y comercial en un control de etiqueta, en lugar de usarlos para crear teclas de acceso.</span><span class="sxs-lookup"><span data-stu-id="2245a-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="2245a-115">Esto puede ocurrir si enlaza un control de etiqueta a un campo en un conjunto de registros donde los datos incluyen símbolos de y comercial.</span><span class="sxs-lookup"><span data-stu-id="2245a-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="2245a-116">Para mostrar una y comercial en un control label, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="2245a-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="2245a-117">Si desea mostrar una y comercial y también tienen una clave de acceso, establecer el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true` e indique la tecla de acceso con una y comercial (&) y la y comercial para mostrar con dos signos de y comercial.</span><span class="sxs-lookup"><span data-stu-id="2245a-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2245a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2245a-118">See Also</span></span>  
 [<span data-ttu-id="2245a-119">Cambiar el tamaño de un control Label de formularios Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="2245a-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [<span data-ttu-id="2245a-120">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="2245a-120">Label Control Overview</span></span>](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [<span data-ttu-id="2245a-121">Etiqueta (control)</span><span class="sxs-lookup"><span data-stu-id="2245a-121">Label Control</span></span>](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
