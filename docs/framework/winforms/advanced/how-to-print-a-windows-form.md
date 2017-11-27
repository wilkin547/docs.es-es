---
title: "Cómo: Imprimir Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9149b90317036c7c62c5fca3056bb697df56e543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-print-a-windows-form"></a>Cómo: Imprimir Windows Forms
Como parte del proceso de desarrollo, normalmente deseará imprimir una copia de los formularios Windows Forms. En el ejemplo de código siguiente se muestra cómo imprimir una copia del formulario actual mediante el uso de la <xref:System.Drawing.Graphics.CopyFromScreen%2A> método.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Éste es un ejemplo de código completo que contiene un `Main` método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No tiene permiso para tener acceso a la impresora.  
  
-   No hay ninguna impresora instalada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Para ejecutar este ejemplo de código, debe tener permiso para tener acceso a la impresora que utilice con el equipo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Representar imágenes con GDI+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [Cómo: Imprimir gráficos en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
