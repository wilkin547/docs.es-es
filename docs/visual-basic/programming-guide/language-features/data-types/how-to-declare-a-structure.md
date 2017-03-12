---
title: "C&#243;mo: Declarar una estructura (Visual Basic) | Microsoft Docs"
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
  - "declaraciones, estructuras"
  - "instrucciones [Visual Basic], estructura"
  - "instrucciones de estructura"
  - "estructuras, declarar"
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Declarar una estructura (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una declaración de estructuras empieza con la instrucción [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md) y finaliza con la instrucción `End` `Structure`.  Entre estas dos instrucciones debe declararse por lo menos un *elemento*.  Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no compartido y no personalizado.  
  
 No puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura.  Al declarar una variable como un tipo de estructura, le asigna valores a los elementos al obtener acceso a los mismos mediante la variable.  
  
 Para obtener una descripción de las diferencias entre estructuras y clases, consulte [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Para efectos demostrativos, considere una situación en la que desee mantener el seguimiento del nombre de un empleado, extensión de teléfono y sueldo.  Una estructura le permite hacer esto en una variable única.  
  
### Para declarar una estructura  
  
1.  Cree las instrucciones de principio y fin para la estructura.  
  
     Puede especificar el nivel de acceso de una estructura mediante la palabra clave [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) o [Private](../../../../visual-basic/language-reference/modifiers/private.md), o puede dejar el valor predeterminado `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Agregar elementos al cuerpo de la estructura.  
  
     Una estructura debe tener al menos un elemento.  Debe declarar cada elemento y especificar un nivel de acceso para el mismo.  Si utiliza la instrucción [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) sin palabras clave, la accesibilidad se establece de forma predeterminada en `Public`.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     El campo `salary` del ejemplo anterior es `Private`, es decir que es inaccesible fuera de la estructura, incluso desde la clase contenedora.  Sin embargo, el procedimiento `giveRaise` es `Public`, así que es posible llamarlo desde fuera de la estructura.  De forma similar, puede provocar el evento `salaryReviewTime` desde fuera de la estructura.  
  
     Además de las variables, procedimientos `Sub` y eventos, también puede definir constantes, procedimientos `Function` y propiedades en una estructura.  Puede designar  como máximo una propiedad como *propiedad predeterminada*, siempre que admita al menos un argumento.  Es posible controlar un evento con un procedimiento [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub`.  Para obtener más información, vea [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Variables de estructura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Tipo de datos definido por el usuario](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)