---
title: "How to: Handle User Input Events in Windows Forms Controls | Microsoft Docs"
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
  - "Windows Forms controls, user input"
  - "user input, Windows Forms controls"
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Handle User Input Events in Windows Forms Controls
En este ejemplo, se muestra cómo controlar la mayoría de los eventos de teclado, mouse, foco y validación que pueden producirse en un control de Windows Forms.  El cuadro de texto denominado `TextBoxInput` recibe los eventos cuando tiene foco y la información sobre cada evento se escribe en el cuadro de texto denominado `TextBoxOutput` en el orden en que se producen los eventos.  La aplicación también incluye un conjunto de casillas que puede utilizarse para filtrar los eventos de los que se quiere dar parte.  
  
## Ejemplo  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 [User Input in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)