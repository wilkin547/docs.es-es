---
title: "No se puede hacer referencia a un miembro de instancia de una clase desde un m&#233;todo compartido o un inicializador de m&#233;todo compartido sin una instancia expl&#237;cita de la clase | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30369"
  - "bc30369"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30369"
  - "Shared"
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede hacer referencia a un miembro de instancia de una clase desde un m&#233;todo compartido o un inicializador de m&#233;todo compartido sin una instancia expl&#237;cita de la clase
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ha intentado hacer referencia a un miembro no compartido de una clase desde dentro de un procedimiento compartido.  El ejemplo siguiente muestra este tipo de situación.  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 En el ejemplo anterior, la instrucción de asignación `x = 10` genera este mensaje de error.  Esto es porque un procedimiento compartido está intentando tener acceso a una variable de instancia.  
  
 La variable `x` es un miembro de instancia porque no se declara como [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  Cada instancia de clase `sample` contiene su propia variable `x` individual.  Cuando una instancia establece o cambia el valor de `x`, no afecta al valor de `x` de ninguna otra instancia.  
  
 Sin embargo, el procedimiento `setX` es `Shared` entre todas las instancias de clase `sample`.  Esto significa que no está asociado con ninguna instancia de la clase, sino que funciona independientemente de las instancias individuales.  Dado que no tiene ninguna conexión con una instancia determinada, `setX` no puede tener acceso a una variable de instancia.  Sólo debe funcionar en variables `Shared`.  Cuando `setX` establece o cambia el valor de una variable compartida, este nuevo valor está disponible para todas las instancias de la clase.  
  
 **Identificador de error:** BC30369  
  
### Para corregir este error  
  
1.  Decida si desea compartir el miembro entre todas las instancias de la clase o que sea individual para cada instancia.  
  
2.  Si desea compartir una copia única del miembro entre todas las instancias, agregue la palabra clave `Shared` a la declaración de miembro.  Incluya la palabra clave `Shared` en la declaración de procedimiento.  
  
3.  Si desea que cada instancia tenga su propia copia individual del miembro, no especifique `Shared` para la declaración de miembro.  Quite la palabra clave `Shared` de la declaración de procedimiento.  
  
## Vea también  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)