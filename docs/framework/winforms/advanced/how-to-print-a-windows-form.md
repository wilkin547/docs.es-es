---
title: "How to: Print a Windows Form | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Windows Forms, printing"
  - "printing [Windows Forms]"
  - "printing a form"
  - "printing [Windows Forms, printing a form"
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Print a Windows Form
Como parte del proceso de desarrollo, normalmente va a imprimir una copia de un Windows Form.  En el ejemplo de código siguiente se muestra cómo imprimir una copia del formulario actual mediante el método <xref:System.Drawing.Graphics.CopyFromScreen%2A>.  
  
## Ejemplo  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## Compilar el código  
 Éste es un ejemplo de código completo que contiene un método `Main`.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   No tiene permiso de acceso a la impresora.  
  
-   No hay ninguna impresora instalada.  
  
## Seguridad de .NET Framework  
 Para poder ejecutar este ejemplo de código, debe tener permiso de acceso a la impresora que utiliza con el equipo.  
  
## Vea también  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Cómo: Representar imágenes con GDI\+](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)   
 [How to: Print Graphics in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)