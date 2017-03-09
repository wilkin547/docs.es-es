---
title: "C&#243;mo: Controlar la disponibilidad de una variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "niveles de acceso, elementos declarados"
  - "niveles de acceso, variables"
  - "elementos declarados, nivel de acceso"
  - "Friend (palabra clave), obtener acceso a variables"
  - "Private (palabra clave), obtener acceso a variables"
  - "Protected (palabra clave), obtener acceso a variables"
  - "Public (palabra clave), obtener acceso a variables"
  - "variables [Visual Basic], nivel de acceso"
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Controlar la disponibilidad de una variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La disponibilidad de una variable se controla especificando su *nivel de acceso*.  El nivel de acceso determina qué código tiene permiso de lectura o escritura en la variable.  
  
-   Las *variables miembros* \(definidas en el nivel de módulo y fuera de cualquier procedimiento\) tienen como valor predeterminado un acceso público que significa cualquier código que puede verlas y tener acceso a ellas.  Puede cambiar esto especificando un modificador de acceso.  
  
-   Las *variables locales* \(definidas dentro de un procedimiento\) tienen nominalmente un acceso público, aunque sólo el código dentro de su procedimiento puede tener acceso a ellas.  No puede cambiar el nivel de acceso de una variable local pero puede cambiar el nivel de acceso del procedimiento que la contiene.  
  
 Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Acceso privado y público  
  
#### Para hacer que una variable sea accesible únicamente desde su módulo, clase o estructura  
  
1.  Coloque la instrucción [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Private](../../../../visual-basic/language-reference/modifiers/private.md) en la instrucción `Dim`.  
  
     Puede leer o escribir en la variable desde cualquier parte dentro del módulo, clase o estructura, pero no desde fuera de él.  
  
#### Para hacer que una variable sea accesible desde cualquier código que puede verla  
  
1.  Para una variable miembro, coloque la instrucción `Dim` para la variable dentro del módulo, clase o estructura pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md) en la instrucción `Dim`.  
  
     Puede leer o escribir en la variable desde cualquier código que interopere con su ensamblado.  
  
 O bien  
  
1.  Para una variable local, coloque la instrucción `Dim` para la variable dentro de un procedimiento.  
  
2.  No incluya la palabra clave `Public` en la instrucción `Dim`.  
  
     Puede leer o escribir en la variable desde cualquier parte dentro del procedimiento pero no desde fuera de él.  
  
## Acceso protegido y amigo  
 Puede limitar el nivel de acceso de una variable a su clase y cualquier clase derivada o a su ensamblado.  También puede especificar la unión de estas limitaciones que permiten el acceso desde un código de cualquier clase derivada o de cualquier otro lugar del mismo ensamblado.  Especifica esta unión combinando las palabras clave `Protected` y `Friend` en la misma declaración.  
  
#### Para hacer que una variable sea accesible desde su clase y cualquier clase derivada  
  
1.  Coloque la instrucción `Dim` para la variable dentro de una clase, pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) en la instrucción `Dim`.  
  
     Puede leer o escribir en la variable desde cualquier parte dentro de la clase, así como desde dentro de cualquier clase derivada de ella pero no desde fuera de cualquier clase de la cadena de derivación.  
  
#### Para hacer que una variable sea accesible sólo desde el mismo ensamblado  
  
1.  Coloque la instrucción `Dim` para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.  
  
2.  Incluya la palabra clave [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) en la instrucción `Dim`.  
  
     Puede leer o escribir en la variable desde cualquier parte dentro del módulo, clase o estructura, así como desde cualquier código del mismo ensamblado pero no desde fuera del ensamblado.  
  
## Ejemplo  
 El ejemplo siguiente muestra declaraciones de variables con niveles de acceso `Public`, `Protected`, `Friend`, `Protected Friend` y `Private`.  Tenga en cuenta que cuando la instrucción `Dim` especifica un nivel de acceso, no necesita incluir la palabra clave `Dim`.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## Seguridad de .NET Framework  
 Cuanto más restrictivo sea el nivel de acceso de una variable, menos posibilidades habrá de que un código malintencionado puede hacer un uso indebido de ella.  
  
## Vea también  
 [Niveles de acceso en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)