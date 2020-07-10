---
title: Procedimiento para imprimir un formulario Windows Forms
description: Obtenga información sobre cómo imprimir mediante programación una copia del formulario de Windows Forms actual mediante el método CopyFromScreen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: b59ea4b5347903b36a166c4f8ac0d8d7db18635e
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174697"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="73947-103">Procedimiento para imprimir un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73947-103">How to: Print a Windows Form</span></span>
<span data-ttu-id="73947-104">Como parte del proceso de desarrollo, normalmente querrá imprimir una copia del formulario de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="73947-104">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="73947-105">En el ejemplo de código siguiente se muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.</span><span class="sxs-lookup"><span data-stu-id="73947-105">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73947-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73947-106">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="73947-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="73947-107">Robust Programming</span></span>  
 <span data-ttu-id="73947-108">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="73947-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="73947-109">No tiene permiso para obtener acceso a la impresora.</span><span class="sxs-lookup"><span data-stu-id="73947-109">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="73947-110">No hay ninguna impresora instalada.</span><span class="sxs-lookup"><span data-stu-id="73947-110">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="73947-111">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="73947-111">.NET Framework Security</span></span>  
 <span data-ttu-id="73947-112">Para ejecutar este ejemplo de código, debe tener permiso de acceso a la impresora que se usa con el equipo.</span><span class="sxs-lookup"><span data-stu-id="73947-112">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73947-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="73947-113">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="73947-114">Procedimiento para representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="73947-114">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="73947-115">Cómo: Imprimir gráficos en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73947-115">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
