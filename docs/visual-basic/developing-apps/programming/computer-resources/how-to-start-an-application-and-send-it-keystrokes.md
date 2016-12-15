---
title: "C&#243;mo: Iniciar una aplicaci&#243;n y enviarle pulsaciones de teclas (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "pulsaciones de teclas, enviar"
  - "procesos, iniciar y enviar pulsaciones de teclas"
  - "Ejemplos de SendKeys.SendWait"
  - "Ejemplo de comandos de shell [Visual Basic]"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Iniciar una aplicaci&#243;n y enviarle pulsaciones de teclas (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este ejemplo se utiliza la función `Shell` para iniciar la aplicación de la calculadora y, a continuación, se multiplican dos números enviando pulsaciones de tecla mediante el método `My.Computer.Keyboard.SendKeys`.  
  
## Ejemplo  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## Programación eficaz  
 Se produce una excepción <xref:System.ArgumentException> si no se puede encontrar una aplicación con el identificador de proceso solicitado.  
  
## Seguridad de .NET Framework  
 La llamada a la función `Shell` requiere plena confianza \(clase <xref:System.Security.SecurityException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>