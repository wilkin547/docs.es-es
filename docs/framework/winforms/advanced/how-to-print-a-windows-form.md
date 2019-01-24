---
title: Procedimiento Imprimir un formulario de Windows
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
ms.openlocfilehash: 5e672f40797a90111daefed0be74c941d4cc37b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628141"
---
# <a name="how-to-print-a-windows-form"></a>Procedimiento Imprimir un formulario de Windows
Como parte del proceso de desarrollo, normalmente deseará imprimir una copia del formulario Windows Forms. El ejemplo de código siguiente muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Este es un ejemplo de código completo que contiene un `Main` método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No tiene permiso para tener acceso a la impresora.  
  
-   No hay ninguna impresora instalada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Printing.PrintDocument>
- [Cómo: Representar imágenes con GDI +](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)
- [Cómo: Imprimir gráficos en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
