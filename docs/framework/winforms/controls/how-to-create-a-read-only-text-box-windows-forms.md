---
title: Filtrar Crear un cuadro de texto de sólo lectura (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 0a29e1c4dcb0bcc8e7d292725e64ea967e160d06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707760"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="4a925-102">Filtrar Crear un cuadro de texto de sólo lectura (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4a925-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="4a925-103">Puede transformar un cuadro de texto editable de Windows Forms en un control de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4a925-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="4a925-104">Por ejemplo, el cuadro de texto puede mostrar un valor que se puede editar normalmente pero actualmente, no puede ser debido al estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a925-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="4a925-105">Para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="4a925-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="4a925-106">Establecer el <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="4a925-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="4a925-107">Con la propiedad establecida en `true`, los usuarios pueden desplazarse y resaltar texto en un cuadro de texto sin permitir que los cambios.</span><span class="sxs-lookup"><span data-stu-id="4a925-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="4a925-108">Un **copia** comando es funcional en un cuadro de texto, pero **cortar** y **pegar** no son de comandos.</span><span class="sxs-lookup"><span data-stu-id="4a925-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4a925-109">El <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4a925-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="4a925-110">Se puede modificar el contenido del cuadro de texto mediante programación en tiempo de ejecución mediante el <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="4a925-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a925-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a925-111">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4a925-112">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="4a925-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4a925-113">Cómo: Controlar el punto de inserción en un Control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a925-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a925-114">Cómo: Crear un cuadro de texto de contraseña con el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a925-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a925-115">Cómo: Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="4a925-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4a925-116">Cómo: Seleccionar texto en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a925-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a925-117">Cómo: Ver múltiples líneas en el Control TextBox de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4a925-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4a925-118">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="4a925-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
