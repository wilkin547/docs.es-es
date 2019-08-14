---
title: Procedimiento Crear un cuadro de texto de solo lectura (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 18d2f5ed2530957487ac25c3eb6240f8bc50a938
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971940"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="7ccb0-102">Procedimiento Crear un cuadro de texto de solo lectura (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7ccb0-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="7ccb0-103">Puede transformar un cuadro de texto Windows Forms editable en un control de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="7ccb0-104">Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita, pero que puede que no sea actualmente, debido al estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="7ccb0-105">Para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="7ccb0-105">To create a read-only text box</span></span>

1. <span data-ttu-id="7ccb0-106">Establezca la <xref:System.Windows.Forms.TextBox> propiedad del <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> control en `true`.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="7ccb0-107">Con la propiedad establecida en `true`, los usuarios todavía pueden desplazarse y resaltar el texto en un cuadro de texto sin permitir cambios.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="7ccb0-108">Un comando de **copia** funciona en un cuadro de texto, pero no los comandos de **cortar** y **pegar** .</span><span class="sxs-lookup"><span data-stu-id="7ccb0-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ccb0-109">La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="7ccb0-110">Todavía puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución <xref:System.Windows.Forms.TextBox.Text%2A> cambiando la propiedad del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="7ccb0-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ccb0-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ccb0-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="7ccb0-112">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="7ccb0-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="7ccb0-113">Cómo: Controlar el punto de inserción en un control de cuadro de texto Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ccb0-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="7ccb0-114">Cómo: Crear un cuadro de texto de contraseña con el control Windows Forms TextBox</span><span class="sxs-lookup"><span data-stu-id="7ccb0-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7ccb0-115">Procedimientos: Insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="7ccb0-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="7ccb0-116">Cómo: Seleccionar texto en el control TextBox Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ccb0-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7ccb0-117">Cómo: Ver varias líneas en el control TextBox Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ccb0-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="7ccb0-118">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="7ccb0-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
