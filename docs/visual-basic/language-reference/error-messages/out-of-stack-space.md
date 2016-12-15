---
title: "Espacio de pila insuficiente (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID28"
dev_langs: 
  - "VB"
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Espacio de pila insuficiente (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La pila es un área de trabajo de memoria que aumenta y disminuye dinámicamente con las demandas del programa en ejecución.  Se han superado los límites.  
  
### Para corregir este error  
  
1.  Compruebe que los procedimientos no estén profundamente anidados.  
  
2.  Asegúrese de que los procedimientos recursivos terminan correctamente.  
  
3.  Si las variables locales requieren más espacio de variable local que el disponible, intente declarar algunas variables en el nivel del módulo.  También puede declarar todas las variables estáticas en el procedimiento anteponiendo a la palabra clave `Property`, `Sub` o `Function` la palabra `Static`.  O puede utilizar la instrucción `Static` para declarar variables estáticas individuales dentro de los procedimientos.  
  
4.  Vuelva a definir algunas de sus cadenas de longitud fija como cadenas de longitud variable, ya que las cadenas de longitud fija utilizan más espacio de pila que las de longitud variable.  También puede definir la cadena en el nivel del módulo donde no se requiere espacio de pila.  
  
5.  Compruebe el número de llamadas a función `DoEvents` anidadas, utilizando el cuadro de diálogo `Calls` para ver qué procedimientos están activos en la pila.  
  
6.  Asegúrese de que no ha provocado "eventos en cascada" al desencadenar el evento que llama al procedimiento de evento que ya está en la pila.  Un evento en cascada es similar a una llamada a procedimientos recursiva e indefinida, pero es menos evidente, dado que la llamada se realiza mediante [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] en lugar de tratarse de una llamada explícita en el código.  Utilice el cuadro de diálogo `Calls` para ver qué procedimientos están activos en la pila.  
  
## Vea también  
 [Memoria \(Ventana\)](/visual-studio/debugger/memory-windows)