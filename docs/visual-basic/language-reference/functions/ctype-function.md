---
title: "CType (Funci&#243;n) (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.CType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "resultados de conversión de expresiones"
  - "conversiones explícitas de tipos de datos"
  - "CType (función)"
  - "conversiones, expresión"
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# CType (Funci&#243;n) (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Devuelve el resultado de convertir explícitamente una expresión en un tipo de datos, objeto, estructura, clase o interfaz especificados.  
  
## Sintaxis  
  
```  
CType(expression, typename)  
```  
  
## Elementos  
 `expression`  
 Cualquier expresión válida.  Si el valor de `expression` está fuera del intervalo permitido por `typename`, Visual Basic produce una excepción.  
  
 `typename`  
 Cualquier expresión válida dentro de una cláusula `As` de una instrucción `Dim`, es decir, el nombre de cualquier tipo de datos, objeto, estructura, clase o interfaz.  
  
## Comentarios  
  
> [!TIP]
>  También puede utilizar las siguientes funciones para realizar una conversión de tipos:  
>   
>  -   La conversión de tipos funciona como `CByte`, `CDbl` y `CInt` que realizan una conversión a un tipo de datos específico.  Para obtener más información, vea [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
> -   [DirectCast \(Operador\)](../../../visual-basic/language-reference/operators/directcast-operator.md) o [TryCast \(Operador\)](../../../visual-basic/language-reference/operators/trycast-operator.md).  Estos operadores requieren que un tipo se herede o implemente en otro tipo.  Pueden proporcionar un mejor rendimiento que `CType` al convertir al tipo de datos de `Object`.  
  
 `CType` se compila en línea, es decir, el código de conversión forma parte del código que evalúa la expresión.  En algunos casos, el código se ejecuta con mayor rapidez porque no se llama a los procedimientos para realizar la conversión.  
  
 Si no se ha definido ninguna conversión de `expression` a `typename`, \(por ejemplo, de `Integer` a `Date`\), Visual Basic muestra un mensaje de error de compilación.  
  
 Si en una conversión se produce un error en tiempo de ejecución, se produce la excepción correspondiente.  Si se produce un error en una conversión de restricción, <xref:System.OverflowException> es el resultado más común.  Si la conversión es indefinida, se produce una excepción <xref:System.InvalidCastException>.  Por ejemplo, esto puede pasar si `expression` es de tipo `Object` y su tipo en tiempo de ejecución no tiene ninguna conversión a `typename`.  
  
 Si el tipo de datos de `expression` o `typename` es una clase o estructura que ha definido, puede definir `CType` en dicha clase o estructura como un operador de conversión.  Esto hace que `CType` actúe como un *operador sobrecargado*.  De este modo, puede controlar el comportamiento de las conversiones que tienen como destino o como origen la clase o estructura, incluidas las excepciones que se pueden producir.  
  
## Sobrecarga  
 El operador `CType` también se puede sobrecargar en una clase o la estructura definida fuera del código.  Si el código realiza conversiones que tienen como destino o como origen una clase o estructura de este tipo, asegúrese de conocer el comportamiento de su operador `CType`.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Convertir objetos dinámicos  
 Las conversiones de tipos de objetos dinámicos se realizan mediante conversiones dinámicas definidas por el usuario que utilizan los métodos <xref:System.Dynamic.DynamicObject.TryConvert%2A> o <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> .  Si está trabajando con objetos dinámicos, utilice el método de <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> para convertir el objeto dinámico.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la función `CType` para convertir una expresión al tipo de datos `Single`.  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/visualbasic/ctype-function_1.vb)]  
  
 Para obtener otros ejemplos, vea [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).  
  
## Vea también  
 <xref:System.OverflowException>   
 <xref:System.InvalidCastException>   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Funciones de conversión](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Conversión de tipos en .NET Framework](../Topic/Type%20Conversion%20in%20the%20.NET%20Framework.md)