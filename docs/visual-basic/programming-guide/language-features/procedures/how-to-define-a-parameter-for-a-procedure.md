---
title: "C&#243;mo: Definir par&#225;metros para un procedimiento (Visual Basic) | Microsoft Docs"
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
  - "parámetros de procedimientos, definir"
  - "parámetros de procedimientos, definir tipos de datos para"
  - "procedimientos, definir"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Definir par&#225;metros para un procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un *parámetro* permite al código de llamada pasar un valor al procedimiento cuando éste lo invoca.  Los parámetros de un procedimiento se declaran igual que las variables, especificando el nombre y el tipo de datos.  También puede especificarse el mecanismo para pasar argumentos, y si se trata de un parámetro opcional.  
  
 Para obtener más información, vea [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md).  
  
### Para definir un parámetro de procedimiento  
  
1.  En la declaración del procedimiento, agregue el nombre de parámetro a la lista de parámetros del procedimiento, separándolo de otros parámetros mediante comas.  
  
2.  Decida el tipo de datos del parámetro.  
  
3.  Inserte una cláusula `As` después del nombre de parámetro para especificar el tipo de datos.  
  
4.  Decida el mecanismo para pasar los argumentos que desea para el parámetro.  Normalmente los parámetros se transfieren por valor, a menos que desee que el procedimiento pueda cambiar su valor en el código de llamada.  
  
5.  Anteponga [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) al nombre del parámetro para especificar el mecanismo para pasar argumentos.  Para obtener más información, vea [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6.  Si el parámetro es opcional, anteponga [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) al mecanismo para pasar argumentos y, detrás del tipo de datos del parámetro, incluya un signo igual \(`=`\) y un valor predeterminado.  
  
     En el ejemplo siguiente se define el esquema de un procedimiento `Sub` con tres parámetros.  Los dos primeros parámetros son obligatorios, mientras que el tercero es opcional.  Las declaraciones de parámetros están separadas en la lista de parámetros mediante comas.  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     El primer parámetro acepta un objeto  `customer` , y `updateCustomer` puede actualizar directamente la variable transferida a `c` porque el argumento se ha transferido [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  El procedimiento no puede cambiar los valores de los últimos dos argumentos porque se han transferido [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     Si el código de llamada no proporciona un valor para el parámetro  `level` , [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] lo establece en el valor predeterminado, que es 0.  
  
     Si el modificador de comprobación de tipo \([Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) es `Off`, la cláusula `As` es opcional cuando define un parámetro.  Sin embargo, si un parámetro utiliza una cláusula `As`, deberán utilizarla todos ellos.  Si el modificador de comprobación de tipo es `On`, la cláusula `As` es obligatoria en todas las definiciones de parámetros.  
  
     La especificación de tipos de datos para todos los elementos de programación recibe el nombre de *tipado fuerte*.  Cuando se establece `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] se aplica el tipado fuerte.  Esto resulta muy recomendable por las siguientes razones:  
  
    -   Habilita la compatibilidad con IntelliSense® para las variables y los parámetros.  Esto permite ver las propiedades de las variables y otros miembros a medida que se escribe el código.  
  
    -   Permite que el compilador realice la comprobación de tipos.  Permite detectar las instrucciones en las que se pueden producir errores en tiempo de ejecución, como el desbordamiento.  También detecta llamadas a métodos en objetos que no las admiten.  
  
    -   Tiene como consecuencia una ejecución más rápida del código.  Esto se debe en parte a que si no se especifica un tipo de datos para un elemento de programación, el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] asigna el tipo `Object`.  El código compilado tendría que realizar conversiones en ambos sentidos entre `Object` y otros tipos de datos, lo que reduciría el rendimiento.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Procedimientos recursivos](../../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Programación orientada a objetos](../Topic/Object-Oriented%20Programming%20\(C%23%20and%20Visual%20Basic\).md)