---
title: "Variables de estructura (Visual Basic) | Microsoft Docs"
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
  - "variables de estructura"
  - "estructuras, variables de estructura"
  - "estructuras, variables"
  - "variables [Visual Basic], variables de estructura"
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Variables de estructura (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una vez creada una estructura, se pueden declarar variables de procedimiento y de módulo como del mismo tipo.  Por ejemplo, puede crear una estructura que registra información sobre un sistema del equipo.  En el siguiente ejemplo se muestra cómo.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Ahora puede declarar variables de ese tipo:  Esto se muestra en la declaración siguiente:  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  En las clases y módulos, las estructuras declaradas mediante [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) se establecen de forma predeterminada como de acceso público.  Si desea que una estructura sea privada, asegúrese de declararla utilizando la palabra clave [Private](../../../../visual-basic/language-reference/modifiers/private.md).  
  
## Acceso a valores de estructura  
 Para asignar y recuperar valores de los elementos de una variable de estructura, utilice la misma sintaxis que para establecer y obtener propiedades de un objeto.  Coloca al operador de acceso a miembros \(`.`\) entre el nombre de la variable de estructura y el nombre del elemento.  El ejemplo siguiente tiene acceso a los elementos de las variables declaradas previamente como tipo `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## Asignar variables de estructura  
 También puede asignar una variable a otra si ambas son del mismo tipo de estructura.  Se copian todos los elementos de una estructura en los elementos correspondientes de la otra.  Esto se muestra en la declaración siguiente:  
  
```  
yourSystem = mySystem  
```  
  
 Si un elemento de una estructura es de tipo referencia, como `String`, `Object` o matriz, se copia el puntero a los datos.  Si `systemInfo` hubiera incluido una variable de objeto, en el ejemplo anterior se habría copiado el puntero de `mySystem` a `yourSystem` y los cambios realizados en los datos del objeto a través de una estructura habrían surtido efecto al tener acceso a ellos a través de la otra estructura.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Estructuras y otros elementos de programación](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)