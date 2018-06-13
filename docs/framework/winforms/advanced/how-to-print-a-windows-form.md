---
title: 'Cómo: Imprimir Windows Forms'
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
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522274"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="69da0-102">Cómo: Imprimir Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69da0-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="69da0-103">Como parte del proceso de desarrollo, normalmente deseará imprimir una copia de los formularios Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="69da0-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="69da0-104">En el ejemplo de código siguiente se muestra cómo imprimir una copia del formulario actual mediante el uso de la <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.</span><span class="sxs-lookup"><span data-stu-id="69da0-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69da0-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69da0-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69da0-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="69da0-106">Compiling the Code</span></span>  
 <span data-ttu-id="69da0-107">Éste es un ejemplo de código completo que contiene un `Main` método.</span><span class="sxs-lookup"><span data-stu-id="69da0-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="69da0-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="69da0-108">Robust Programming</span></span>  
 <span data-ttu-id="69da0-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="69da0-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="69da0-110">No tiene permiso para tener acceso a la impresora.</span><span class="sxs-lookup"><span data-stu-id="69da0-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="69da0-111">No hay ninguna impresora instalada.</span><span class="sxs-lookup"><span data-stu-id="69da0-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="69da0-112">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="69da0-112">.NET Framework Security</span></span>  
 <span data-ttu-id="69da0-113">Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.</span><span class="sxs-lookup"><span data-stu-id="69da0-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69da0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="69da0-114">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="69da0-115">Representar imágenes con GDI+</span><span class="sxs-lookup"><span data-stu-id="69da0-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [<span data-ttu-id="69da0-116">Cómo: Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69da0-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
