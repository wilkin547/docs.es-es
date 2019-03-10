---
title: Filtrar Crear teclas de acceso con controles Label de formularios de Windows
ms.date: 03/30/2017
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
ms.openlocfilehash: 227880ad15e452df3f05807c41f3923cccb6fe3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708306"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a><span data-ttu-id="34ada-102">Filtrar Crear teclas de acceso con controles Label de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="34ada-102">How to: Create Access Keys with Windows Forms Label Controls</span></span>
<span data-ttu-id="34ada-103">Windows Forms <xref:System.Windows.Forms.Label> controles pueden usarse para definir teclas de acceso para otros controles.</span><span class="sxs-lookup"><span data-stu-id="34ada-103">Windows Forms <xref:System.Windows.Forms.Label> controls can be used to define access keys for other controls.</span></span> <span data-ttu-id="34ada-104">Al definir una clave de acceso en un control de etiqueta, el usuario puede presionar la tecla ALT y el carácter designado para mover el foco al control que le sigue en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="34ada-104">When you define an access key in a label control, the user can press the ALT key plus the character you designate to move the focus to the control that follows it in the tab order.</span></span> <span data-ttu-id="34ada-105">Dado que las etiquetas no pueden recibir el foco, el foco se mueve automáticamente al siguiente control en el orden de tabulación.</span><span class="sxs-lookup"><span data-stu-id="34ada-105">Because labels cannot receive focus, focus automatically moves to the next control in the tab order.</span></span> <span data-ttu-id="34ada-106">Use esta técnica para asignar las claves de acceso a los cuadros de texto, cuadros combinados, cuadros de lista y cuadrículas de datos.</span><span class="sxs-lookup"><span data-stu-id="34ada-106">Use this technique to assign access keys to text boxes, combo boxes, list boxes, and data grids.</span></span>  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a><span data-ttu-id="34ada-107">Para asignar una tecla de acceso a un control con una etiqueta</span><span class="sxs-lookup"><span data-stu-id="34ada-107">To assign an access key to a control with a label</span></span>  
  
1.  <span data-ttu-id="34ada-108">Dibuje primero la etiqueta y, a continuación, dibuje el control de otro.</span><span class="sxs-lookup"><span data-stu-id="34ada-108">Draw the label first, and then draw the other control.</span></span>  
  
     <span data-ttu-id="34ada-109">O bien</span><span class="sxs-lookup"><span data-stu-id="34ada-109">-or-</span></span>  
  
     <span data-ttu-id="34ada-110">Dibuje los controles en cualquier orden y establezca el <xref:System.Windows.Forms.Control.TabIndex%2A> propiedad de la etiqueta a menos que el otro control.</span><span class="sxs-lookup"><span data-stu-id="34ada-110">Draw the controls in any order and set the <xref:System.Windows.Forms.Control.TabIndex%2A> property of the label to one less than the other control.</span></span>  
  
2.  <span data-ttu-id="34ada-111">Establezca la etiqueta <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="34ada-111">Set the label's <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="34ada-112">Utilice una y comercial (&) en la etiqueta <xref:System.Windows.Forms.Label.Text%2A> propiedad para asignar la clave de acceso para la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="34ada-112">Use an ampersand (&) in the label's <xref:System.Windows.Forms.Label.Text%2A> property to assign the access key for the label.</span></span> <span data-ttu-id="34ada-113">Para obtener más información, consulte [crear teclas de acceso para controles de formularios Windows Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="34ada-113">For more information, see [Creating Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="34ada-114">Es posible que desee mostrar una y comercial en un control de etiqueta, en lugar de usar para crear claves de acceso.</span><span class="sxs-lookup"><span data-stu-id="34ada-114">You may want to display ampersands in a label control, rather than use them to create access keys.</span></span> <span data-ttu-id="34ada-115">Esto puede ocurrir si enlaza un control de etiqueta a un campo en un conjunto de registros donde los datos incluyen los y comerciales.</span><span class="sxs-lookup"><span data-stu-id="34ada-115">This may occur if you bind a label control to a field in a recordset where the data includes ampersands.</span></span> <span data-ttu-id="34ada-116">Para mostrar una y comercial en un control label, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="34ada-116">To display ampersands in a label control, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `false`.</span></span> <span data-ttu-id="34ada-117">Si desea mostrar una y comercial y tener también una clave de acceso, establezca el <xref:System.Windows.Forms.Label.UseMnemonic%2A> propiedad `true` e indique la clave de acceso con una y comercial (&) y la y comercial para mostrar con dos signos de y comercial.</span><span class="sxs-lookup"><span data-stu-id="34ada-117">If you wish to display ampersands and also have an access key, set the <xref:System.Windows.Forms.Label.UseMnemonic%2A> property to `true` and indicate the access key with one ampersand (&) and the ampersand to display with two ampersands.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34ada-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="34ada-118">See also</span></span>
- [<span data-ttu-id="34ada-119">Cómo: Tamaño de un Control de etiqueta de Windows Forms para ajustar su contenido</span><span class="sxs-lookup"><span data-stu-id="34ada-119">How to: Size a Windows Forms Label Control to Fit Its Contents</span></span>](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [<span data-ttu-id="34ada-120">Información general sobre el control Label</span><span class="sxs-lookup"><span data-stu-id="34ada-120">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="34ada-121">Etiqueta (control)</span><span class="sxs-lookup"><span data-stu-id="34ada-121">Label Control</span></span>](label-control-windows-forms.md)
