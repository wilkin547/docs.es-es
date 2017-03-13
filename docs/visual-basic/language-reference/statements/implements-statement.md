---
title: "Implements (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Implements"
  - "Implements"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Implements (instrucción)"
  - "Implements (instrucción), sintaxis"
  - "implementación de interfaces, Implements (instrucción)"
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Implements (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica una o más interfaces o miembros de interfaz que se deben implementar en la definición de clase o estructura en la que aparecen.  
  
## Sintaxis  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## Elementos  
 `interfacename`  
 Obligatorio.  Una interfaz cuyas propiedades, procedimientos y eventos deben implementarse por los miembros correspondientes de la clase o estructura.  
  
 `interfacemember`  
 Obligatorio.  El miembro de una interfaz que se va a implementar.  
  
## Comentarios  
 Una interfaz es una colección de prototipos que representan los miembros \(propiedades, procedimientos y eventos\) que encapsula la interfaz.  Las interfaces sólo contienen las declaraciones para miembros. Las clases y estructuras implementan estos miembros.  Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 La instrucción `Implements` debe incluirse inmediatamente a continuación de las instrucciones `Class` o `Structure`.  
  
 Cuando implementa una interfaz, debe implementar todos los miembros declarados en la interfaz.  Se considera un error de sintaxis omitir cualquier miembro.  Para implementar un miembro concreto, se especifica la palabra clave [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) \(que es independiente de la instrucción `Implements`\) al declarar el miembro en la clase o la estructura.  Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Las clases pueden utilizar implementaciones [Private](../../../visual-basic/language-reference/modifiers/private.md) de propiedades y procedimientos, pero estos miembros sólo son accesibles convirtiendo una instancia de la clase que se implementa en una variable declarada para ser del tipo de la interfaz.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo utilizar la instrucción `Implements` para implementar miembros de una interfaz.  Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento.  La clase `customerInfo` implementa todos los miembros definidos en la interfaz.  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 Observe que la clase `customerInfo` utiliza la instrucción `Implements` de una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la interfaz `ICustomerInfo`.  A continuación, cada miembro de la clase utiliza la palabra clave `Implements` como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.  
  
## Ejemplo  
 Los dos procedimientos siguientes muestran cómo se podría utilizar la interfaz implementada en el ejemplo anterior.  Para comprobar la implementación, agregue estos procedimientos al proyecto e invoque el procedimiento `testImplements`.  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## Vea también  
 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)