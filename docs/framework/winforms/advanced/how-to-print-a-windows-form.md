---
title: Filtrar para imprimir un formulario Windows Forms
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
ms.openlocfilehash: 85fb12028687578b76e0f16061deb9b9a4de70e3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121971"
---
# <a name="how-to-print-a-windows-form"></a>Filtrar para imprimir un formulario Windows Forms
Como parte del proceso de desarrollo, normalmente deseará imprimir una copia del formulario Windows Forms. El ejemplo de código siguiente muestra cómo imprimir una copia del formulario actual mediante el <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
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
- [Filtrar para representar imágenes con GDI+](how-to-render-images-with-gdi.md)
- [Filtrar para imprimir gráficos en formularios Windows Forms](how-to-print-graphics-in-windows-forms.md)
