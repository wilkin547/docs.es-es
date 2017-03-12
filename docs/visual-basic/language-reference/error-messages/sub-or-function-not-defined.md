---
title: "Sub o Function no definida (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID35"
dev_langs: 
  - "VB"
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Sub o Function no definida (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Para realizar una llamada a `Sub` o `Function` deben definirse.  Las causas posibles de este error son:  
  
-   Se ha escrito mal el nombre de procedimiento.  
  
-   Se intenta llamar a un procedimiento desde otro proyecto sin agregar explícitamente una referencia a ese proyecto en el cuadro de diálogo **Referencias**.  
  
-   Se ha especificado un procedimiento que no es visible para el procedimiento que llama.  
  
-   Se ha declarado una rutina de biblioteca de vínculos dinámicos \(DLL\) Windows o una rutina de recursos del código Macintosh que no se encuentra en la biblioteca o el recurso del código especificados.  
  
### Para corregir este error  
  
1.  Asegúrese de que el nombre de procedimiento está correctamente escrito.  
  
2.  Busque el nombre del proyecto que contiene el procedimiento al que desea llamar en el cuadro de diálogo **Referencias**.  Si no aparece, haga clic en el botón **Examinar** para buscarlo.  Active la casilla situada a la izquierda del nombre de proyecto y haga clic en **Aceptar**.  
  
3.  Compruebe el nombre de la rutina.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Administrar referencias en un proyecto](/visual-studio/ide/managing-references-in-a-project)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)