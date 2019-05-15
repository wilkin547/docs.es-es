---
title: Procedimiento para imprimir un formulario Windows Forms
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
ms.openlocfilehash: cd10e0a43ff37b921dc8e024d7a6a51fafbb0400
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591851"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="a5ab2-102">Procedimiento para imprimir un formulario Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5ab2-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="a5ab2-103">Como parte del proceso de desarrollo, normalmente deseará imprimir una copia del formulario Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5ab2-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="a5ab2-104">El ejemplo de código siguiente muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.</span><span class="sxs-lookup"><span data-stu-id="a5ab2-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ab2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5ab2-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a5ab2-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a5ab2-106">Robust Programming</span></span>  
 <span data-ttu-id="a5ab2-107">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="a5ab2-107">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="a5ab2-108">No tiene permiso para tener acceso a la impresora.</span><span class="sxs-lookup"><span data-stu-id="a5ab2-108">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="a5ab2-109">No hay ninguna impresora instalada.</span><span class="sxs-lookup"><span data-stu-id="a5ab2-109">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a5ab2-110">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a5ab2-110">.NET Framework Security</span></span>  
 <span data-ttu-id="a5ab2-111">Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.</span><span class="sxs-lookup"><span data-stu-id="a5ab2-111">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ab2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5ab2-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="a5ab2-113">Cómo: Representar imágenes con GDI +</span><span class="sxs-lookup"><span data-stu-id="a5ab2-113">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="a5ab2-114">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5ab2-114">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
