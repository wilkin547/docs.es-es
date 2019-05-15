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
# <a name="how-to-print-a-windows-form"></a>Procedimiento para imprimir un formulario Windows Forms
Como parte del proceso de desarrollo, normalmente deseará imprimir una copia del formulario Windows Forms. El ejemplo de código siguiente muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
- No tiene permiso para tener acceso a la impresora.  
  
- No hay ninguna impresora instalada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Printing.PrintDocument>
- [Cómo: Representar imágenes con GDI +](how-to-render-images-with-gdi.md)
- [Cómo: Imprimir gráficos en Windows Forms](how-to-print-graphics-in-windows-forms.md)
