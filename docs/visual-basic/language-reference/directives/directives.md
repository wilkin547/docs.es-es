---
title: "Directivas de Visual Basic | Microsoft Docs"
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
  - "directivas"
  - "directivas, compilador de Visual Basic"
  - "código de Visual Basic, directivas"
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Directivas de Visual Basic
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Los temas en esta sección documentan las directivas del compilador de código fuente de Visual Basic.  
  
## En esta sección  
 [\#Const \(Directiva\)](../../../visual-basic/language-reference/directives/const-directive.md): define una constante del compilador.  
  
 [\#ExternalSource \(Directiva\)](../../../visual-basic/language-reference/directives/externalsource-directive.md): indica una asignación entre líneas de código fuente y texto externo al código fuente.  
  
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md): compilan bloques de código seleccionados.  
  
 [\#Region \(Directiva\)](../../../visual-basic/language-reference/directives/region-directive.md): contrae y oculta secciones de código en el editor de Visual Studio.  
  
 **\#Disable, \#Enable**: deshabilita y habilita advertencias específicas para regiones de código.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
  
```  
  
 También puede deshabilitar y habilitar una lista separada por comas de códigos de advertencia.  
  
## Secciones relacionadas  
 [Referencia del lenguaje Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)