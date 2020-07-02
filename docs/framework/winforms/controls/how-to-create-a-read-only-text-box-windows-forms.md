---
title: Procedimiento para crear un cuadro de texto de solo lectura
description: Obtenga información sobre cómo transformar un cuadro de texto Windows Forms editable en un cuadro de texto de Windows Forms de solo lectura.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 5baa7c66d5f16560a4ea23861d563b099592957f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619369"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="3d4a7-103">Cómo: Crear un cuadro de texto de sólo lectura (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3d4a7-103">How to: Create a Read-Only Text Box (Windows Forms)</span></span>

<span data-ttu-id="3d4a7-104">Puede transformar un cuadro de texto Windows Forms editable en un control de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3d4a7-104">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="3d4a7-105">Por ejemplo, el cuadro de texto puede mostrar un valor que normalmente se edita, pero que puede que no sea actualmente, debido al estado de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3d4a7-105">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>

## <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="3d4a7-106">Para crear un cuadro de texto de solo lectura</span><span class="sxs-lookup"><span data-stu-id="3d4a7-106">To create a read-only text box</span></span>

1. <span data-ttu-id="3d4a7-107">Establezca la <xref:System.Windows.Forms.TextBox> propiedad del control <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> en `true` .</span><span class="sxs-lookup"><span data-stu-id="3d4a7-107">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="3d4a7-108">Con la propiedad establecida en `true` , los usuarios todavía pueden desplazarse y resaltar el texto en un cuadro de texto sin permitir cambios.</span><span class="sxs-lookup"><span data-stu-id="3d4a7-108">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="3d4a7-109">Un comando de **copia** funciona en un cuadro de texto, pero no los comandos de **cortar** y **pegar** .</span><span class="sxs-lookup"><span data-stu-id="3d4a7-109">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d4a7-110">La <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> propiedad solo afecta a la interacción del usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3d4a7-110">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="3d4a7-111">Todavía puede cambiar el contenido del cuadro de texto mediante programación en tiempo de ejecución cambiando la <xref:System.Windows.Forms.TextBox.Text%2A> propiedad del cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="3d4a7-111">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>

## <a name="see-also"></a><span data-ttu-id="3d4a7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d4a7-112">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="3d4a7-113">Información general sobre el control TextBox</span><span class="sxs-lookup"><span data-stu-id="3d4a7-113">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="3d4a7-114">Procedimiento para controlar el punto de inserción en un control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d4a7-114">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="3d4a7-115">Procedimiento para crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d4a7-115">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3d4a7-116">Procedimiento para insertar comillas en una cadena</span><span class="sxs-lookup"><span data-stu-id="3d4a7-116">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="3d4a7-117">Procedimiento para seleccionar texto en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d4a7-117">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3d4a7-118">Procedimiento para ver varias líneas en el control TextBox de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3d4a7-118">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3d4a7-119">Control TextBox</span><span class="sxs-lookup"><span data-stu-id="3d4a7-119">TextBox Control</span></span>](textbox-control-windows-forms.md)
