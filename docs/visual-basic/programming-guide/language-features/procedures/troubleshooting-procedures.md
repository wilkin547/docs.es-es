---
title: "Solucionar problemas de procedimientos (Visual Basic) | Microsoft Docs"
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
  - "procedimientos, acerca de los procedimientos"
  - "procedimientos, solucionar problemas"
  - "solucionar problemas de procedimientos"
  - "solucionar problemas de Visual Basic, procedimientos"
  - "código de Visual Basic, procedimientos"
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Solucionar problemas de procedimientos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Esta página muestra algunos problemas comunes que pueden aparecer al trabajar con procedimientos.  
  
## Devolver una matriz de tipo desde un procedimiento de función  
 Si un procedimiento `Function` devuelve un tipo de datos de matriz, no puede utilizar el nombre `Function` para almacenar valores en los elementos de la matriz.  Si se intenta hacerlo, el compilador lo interpreta como una llamada a la función `Function`.  En el siguiente ejemplo se generan errores de compilador.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 La instrucción `allOnes(i) = 1` genera un error de compilador porque llama a `allOnes` con un argumento de tipo de datos erróneo \(un objeto singleton `Integer` en lugar de una matriz `Integer`\).  La instrucción `Return allOnes()` genera un error de compilador porque llama a `allOnes` sin argumento.  
  
 **Enfoque correcto:** para poder modificar los elementos de una matriz que se debe devolver, defina una matriz interna como variable local.  En el siguiente ejemplo se compila sin errores.  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## Argumento no modificado por una llamada a procedimiento  
 Si intenta permitir a un procedimiento que cambie un elemento de programación subyacente a un argumento en el código de llamada, debe pasarlo por referencia.  No obstante, un procedimiento puede tener acceso a los elementos de un argumento de tipo de referencia aun cuando se pase por valor.  
  
-   **Variable subyacente** Para permitir al procedimiento reemplazar el valor del propio elemento variable subyacente, el procedimiento debe declarar el parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).  El código de llamada no debe incluir tampoco el argumento entre paréntesis, porque eso reemplazaría el mecanismo para pasar argumentos `ByRef`.  
  
-   **Elementos de tipo de referencia**.  Si declara un parámetro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), el procedimiento no puede modificar el propio elemento variable subyacente.  No obstante, si el argumento es un tipo de referencia, el procedimiento puede modificar los miembros del objeto al que señala, aunque no puede reemplazar el valor de la variable.  Por ejemplo, si el argumento es una variable de matriz, el procedimiento no puede asignarle otra matriz, pero sí puede cambiar uno o varios de sus elementos.  La modificación de los elementos queda reflejada en la variable de matriz subyacente al código de llamada.  
  
 En el siguiente ejemplo se definen dos procedimientos que aceptan una variable de matriz por valor y operan con sus elementos.  El procedimiento `increase` suma sencillamente una unidad a cada elemento.  El procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento.  La reasignación, sin embargo, no afecta a la variable de matriz subyacente al código de llamada porque `a()` se declara `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 En el ejemplo siguiente se realizan llamadas a `increase` y `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 La primera llamada a `MsgBox` muestra "After increase\(n\): 11, 21, 31, 41".  Como `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque se pase `ByVal`.  
  
 La segunda llamada a `MsgBox` muestra "After replace\(n\): 11, 21, 31, 41".  Como `n` se pasa `ByVal`, `replace` no puede modificar la variable `n` asignándole una nueva matriz.  Cuando `replace` crea una nueva instancia de matriz `k` y la asigna a la variable local `a`, pierde la referencia a `n` que le ha pasado el código de llamada.  Cuando incrementa los miembros de `a`, esto sólo afecta a la matriz local `k`.  
  
 **Enfoque correcto:** para poder modificar un elemento variable subyacente en sí, páselo por referencia.  En el ejemplo siguiente se muestra el cambio en la declaración de `replace` que permite reemplazar una matriz por otra en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## No se puede definir una sobrecarga  
 Si desea definir una versión sobrecargada de un procedimiento, debe utilizar el mismo nombre pero con una firma diferente.  Si el compilador no puede diferenciar su declaración de una sobrecarga con la misma firma, genera un error.  
  
 El nombre de procedimiento y la lista de parámetros determinan la *firma* de un procedimiento.  Cada sobrecarga debe tener el mismo nombre que todas las demás sobrecargas pero debe diferenciarse de todas ellas en al menos uno de los componentes de la firma.  Para obtener más información, vea [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
 Los elementos siguientes, aunque pertenecen a la lista de parámetros, no son componentes de la firma de un procedimiento:  
  
-   Palabras clave que modifican a los procedimientos, como `Public`, `Shared` y `Static`  
  
-   Nombres de parámetros  
  
-   Palabras clave que modifican a los parámetros, como `ByRef` y `Optional`  
  
-   El tipo de datos del valor devuelto \(excepto para un operador de conversión\)  
  
 No es posible sobrecargar un procedimiento cambiando únicamente uno o varios de los elementos anteriores:  
  
 **Enfoque correcto:** para poder definir una sobrecarga de procedimiento, debe variar la firma.  Como debe utilizar el mismo nombre, debe variar el número, orden o tipos de datos de los parámetros.  En un procedimiento genérico, puede variar el número de parámetros de tipo.  En un operador de conversión \([CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md)\), puede variar el tipo de valor devuelto.  
  
### Resolución de sobrecarga con argumentos Optional y ParamArray  
 Si sobrecarga un procedimiento con uno o varios parámetros [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) o un parámetro [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md), debe evitar duplicar las *sobrecargas implícitas*.  Para obtener más información, vea [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md).  
  
## Llamar a una versión incorrecta de un procedimiento sobrecargado  
 Si un procedimiento tiene varias versiones sobrecargadas, debe estar familiarizado con todas las listas de parámetros y comprender cómo resuelve [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] las llamadas entre las sobrecargas.  De lo contrario podría llamar a una sobrecarga distinta de la que desea.  
  
 Cuando haya determinado a qué sobrecarga desea llamar, observe cuidadosamente las reglas siguientes:  
  
-   Proporcione el número correcto de argumentos y en el orden correcto.  
  
-   Lo ideal es que sus argumentos tengan los mismos tipos de datos exactos que los parámetros correspondientes.  En cualquier caso, el tipo de datos de cada argumento debe ampliarse al de su parámetro correspondiente.  Esto es verdad incluso con [Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establecido en `Off`.  Si una sobrecarga requiere cualquier conversión de restricción de la lista de argumentos, no se debe llamar a esta sobrecarga.  
  
-   Si proporciona argumentos que requieren ampliación, haga que sus tipos de datos se acerquen lo más posible a los tipos de datos de los parámetros correspondientes.  Si dos o más sobrecargas aceptan los tipos de datos de argumentos, el compilador resuelve la llamada con la sobrecarga que solicita la menor cantidad de ampliación.  
  
 Puede reducir las posibilidades de que aparezcan discordancias del tipo de datos mediante la palabra clave de conversión [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) cuando prepara los argumentos.  
  
### Error de resolución de sobrecarga  
 Cuando llama a un procedimiento sobrecargado, el compilador intenta eliminar todas menos una de las sobrecargas.  Si lo consigue, resuelve la llamada con esa sobrecarga.  Si elimina todas las sobrecargas o si no puede reducir las sobrecargas seleccionables a un candidato único, genera un error.  
  
 Este proceso de resolución de las sobrecargas se ilustra en el siguiente ejemplo:  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento \(`Short`\) se restringe al tipo del parámetro correspondiente \(`Byte`\).  A continuación, elimina la tercera sobrecarga porque cada tipo de argumento de la segunda sobrecarga \(`Short` y `Single`\) se amplía al tipo correspondiente a la tercera sobrecarga \(`Integer` y `Single`\).  La segunda sobrecarga requiere una ampliación menor, y por eso el compilador la utiliza en la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna sobrecarga teniendo en cuenta la restricción.  Elimina la tercera sobrecarga por el mismo motivo por el que la eliminó en la primera llamada, porque puede llamar a la segunda sobrecarga con una ampliación menor de los tipos de argumentos.  Sin embargo, el compilador no puede decidirse entre la primera y la segunda sobrecarga.  Cada una de ellas tiene un tipo de parámetro definido que se amplía al tipo correspondiente de la otra \(`Byte` a `Short`, pero `Single` a `Double`\).  Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
 **Enfoque correcto:** para poder llamar a un procedimiento sobrecargado sin ambigüedad, utilice [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) para que los tipos de datos de argumentos coincidan con los tipos de parámetros.  En el ejemplo siguiente se muestra una llamada a `z` que fuerza a la resolución a la segunda sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### Resolución de sobrecarga con argumentos Optional y ParamArray  
 Si dos sobrecargas de un procedimiento tienen las mismas firmas excepto que el último parámetro está declarado [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) en una y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en la otra, el compilador resuelve una llamada a ese procedimiento según la coincidencia más próxima.  Para obtener más información, vea [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md).  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedimientos de operador](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)