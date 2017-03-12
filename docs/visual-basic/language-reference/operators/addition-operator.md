---
title: "+ (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.+"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "+ (operador)"
  - "operadores aritméticos, suma"
  - "operadores de concatenación, sintaxis"
  - "cadenas [Visual Basic], concatenar"
  - "operador de suma"
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# + (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Suma dos números o devuelve el valor positivo de una expresión numérica.  También se puede utilizar para concatenar dos expresiones de cadena.  
  
## Sintaxis  
  
```  
  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`expression1`|Obligatorio.  Cualquier expresión numérica o de cadena.|  
|`expression2`|Obligatorio a menos que el operador `+` esté calculando un valor negativo.  Cualquier expresión numérica o de cadena.|  
  
## Resultado  
 Si `expression1` y `expression2` son ambos numéricos, el resultado es su suma aritmética.  
  
 Si `expression2` está ausente, el operador `+` es el operador de identidad *unario* para el valor sin modificar de una expresión.  En este sentido, la operación trata de conservar el signo de `expression1`, por lo que el resultado es negativo si `expression1` es negativo.  
  
 Si `expression1` y `expression2` son ambas cadenas, el resultado es la concatenación de sus valores.  
  
 Si `expression1` y `expression2` son de tipos mixtos, la acción realizada depende de sus tipos, su contenido y la configuración de [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  Para obtener más información, vea las tablas en "Comentarios".  
  
## Tipos admitidos  
 Todos los tipos numéricos, incluidos los tipos de punto flotante y sin signo, `Decimal` y `String`.  
  
## Comentarios  
 En general, `+` realiza la suma aritmética cuando es posible y sólo concatena cuando ambas expresiones son cadenas.  
  
 Si ninguna de las expresiones es `Object`, Visual Basic realiza las acciones siguientes.  
  
|||  
|-|-|  
|Tipos de datos de expresiones|Acción del compilador|  
|Ambas expresiones son tipos de datos numéricos \(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` o `Double`\)|Deberá agregar.  El tipo de datos resultante es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`.  Vea las tablas "Aritmética de enteros" en [Tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Ambas expresiones son de tipo `String`|Deberá concatenar.|  
|Una expresión es numérica y la otra es una cadena|Si `Option Strict` es `On`, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convertir implícitamente `String` en `Double` y sumar.<br /><br /> Si `String` no puede convertirse en `Double`, producir una excepción <xref:System.InvalidCastException>.|  
|Una expresión es numérica y la otra es [Nothing](../../../visual-basic/language-reference/nothing.md)|Sumar, con `Nothing` evaluado como cero.|  
|Una expresión es una cadena y la otra es `Nothing`|Concatenar, con `Nothing` evaluado como " ".|  
  
 Si una de las expresiones es `Object`, Visual Basic realiza las acciones siguientes.  
  
|||  
|-|-|  
|Tipos de datos de expresiones|Acción del compilador|  
|`Object` expresión que contiene un valor numérico y la otra es un tipo de datos numérico|Si `Option Strict` es `On`, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, sumar.|  
|La expresión de `Object` contiene un valor numérico y la otra es de tipo `String`|Si `Option Strict` es `On`, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convertir implícitamente `String` en `Double` y sumar.<br /><br /> Si `String` no puede convertirse en `Double`, producir una excepción <xref:System.InvalidCastException>.|  
|`Object` expresión que contiene una cadena y la otra es un tipo de datos numérico|Si `Option Strict` es `On`, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convertir implícitamente la cadena `Object` en `Double` y sumar.<br /><br /> Si la cadena `Object` no puede convertirse en `Double`, producir una excepción <xref:System.InvalidCastException>.|  
|La expresión de `Object` contiene una cadena y la otra es de tipo `String`|Si `Option Strict` es `On`, generar un error del compilador.<br /><br /> Si `Option Strict` es `Off`, convertir implícitamente `Object` en `String` y concatenar.|  
  
 Si ambas son expresiones `Object`, Visual Basic realiza las acciones siguientes \(sólo `Option Strict Off`\).  
  
|||  
|-|-|  
|Tipos de datos de expresiones|Acción del compilador|  
|Ambas expresiones `Object` contienen valores numéricos|Deberá agregar.|  
|Ambas expresiones `Object` son de tipo `String`|Deberá concatenar.|  
|Una expresión `Object` contiene un valor numérico y la otra, una cadena|Convertir implícitamente la cadena `Object` en `Double` y sumar.<br /><br /> Si la cadena `Object` no puede convertirse en un valor numérico, producir una excepción <xref:System.InvalidCastException>.|  
  
 Si una de las expresiones `Object` se evalúa como [Nothing](../../../visual-basic/language-reference/nothing.md) o <xref:System.DBNull>, el operador `+` la trata como `String` con un valor de " ".  
  
> [!NOTE]
>  Cuando utilice el operador `+`, puede que no logre determinar si se producirá una suma o bien una concatenación de cadenas.  Use el operador `&` de concatenación para eliminar ambigüedades y ofrecer código autoexplicativo.  
  
## Sobrecarga  
 El operador `+` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En el ejemplo siguiente se usa el operador `+` para sumar números.  Si los operandos son ambos numéricos, Visual Basic calcula el resultado aritmético.  El resultado aritmético representa la suma de ambos operandos.  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_1.vb)]  
  
 El operador `+` también puede utilizarse para concatenar cadenas.  Si los operandos son ambos cadenas, Visual Basic los concatena.  El resultado de la concatenación representa una cadena única que consta del contenido de los dos operandos uno tras otro.  
  
 Si los operandos son de tipos mixtos, el resultado depende de la configuración de [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  El ejemplo siguiente ilustra el resultado cuando `Option Strict` es `On`.  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_4.vb)]  
  
 El ejemplo siguiente ilustra el resultado cuando `Option Strict` es `Off`.  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/addition-operator_6.vb)]  
  
 Para eliminar la ambigüedad, debería utilizar al operador `&` en lugar de `+` para la concatenación.  
  
## Vea también  
 [& \(Operador\)](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)