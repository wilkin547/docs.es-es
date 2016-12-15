---
title: "C&#243;mo: Llamar a las API de Windows (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "llamadas API"
  - "llamadas API, invocación de plataforma"
  - "llamadas, procedimientos almacenados"
  - "API de Windows, llamar"
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Llamar a las API de Windows (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

En este ejemplo se define y se llama a la función `MessageBox` de user32.dll y, a continuación, se le pasa una cadena.  
  
## Ejemplo  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System>.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El método no es estático, es abstracto o se ha definido previamente.  El tipo principal es una interfaz o la longitud de *name* o *dllName* es cero.  \(<xref:System.ArgumentException>\)  
  
-   *name* o *dllName* es `Nothing`.  \(<xref:System.ArgumentNullException>\)  
  
-   El tipo contenedor se ha creado previamente mediante `CreateType`.  \(<xref:System.InvalidOperationException>\)  
  
## Vea también  
 [A Closer Look at Platform Invoke](http://msdn.microsoft.com/es-es/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)   
 [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md)   
 [Consuming Unmanaged DLL Functions](../Topic/Consuming%20Unmanaged%20DLL%20Functions.md)   
 [Definir un método con la emisión de la reflexión](http://msdn.microsoft.com/es-es/84fd3bf6-628f-41aa-83d9-b990cf926e81)   
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)   
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)