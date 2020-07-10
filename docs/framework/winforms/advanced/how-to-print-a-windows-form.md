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
# <a name="how-to-print-a-windows-form"></a>Procedimiento para imprimir un formulario Windows Forms
Como parte del proceso de desarrollo, normalmente querrá imprimir una copia del formulario de Windows Forms. En el ejemplo de código siguiente se muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- No tiene permiso para obtener acceso a la impresora.  
  
- No hay ninguna impresora instalada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para ejecutar este ejemplo de código, debe tener permiso de acceso a la impresora que se usa con el equipo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Printing.PrintDocument>
- [Procedimiento para representar imágenes con GDI+](how-to-render-images-with-gdi.md)
- [Cómo: Imprimir gráficos en formularios Windows Forms](how-to-print-graphics-in-windows-forms.md)
