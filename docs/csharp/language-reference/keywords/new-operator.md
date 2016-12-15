---
title: "new (Operador, Referencia de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new (operador, palabra clave) [C#]"
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# new (Operador, Referencia de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se utiliza para crear objetos e invocar constructores.  Por ejemplo:  
  
```  
Class1 obj  = new Class1();  
```  
  
 También se utiliza para crear instancias de tipos anónimos:  
  
```  
var query = from cust in customers  
            select new {Name = cust.Name, Address = cust.PrimaryAddress};  
```  
  
 El operador `new` también se utiliza para invocar el constructor predeterminado de los tipos de valor.  Por ejemplo:  
  
```  
int i = new int();  
```  
  
 En la instrucción anterior se inicializa `i` con el valor `0`, que es el predeterminado para el tipo `int`.  Esa instrucción tiene el mismo efecto que:  
  
```  
int i = 0;  
```  
  
 Para obtener una lista de valores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).  
  
 Recuerde que es un error declarar un constructor predeterminado para un tipo [struct](../../../csharp/language-reference/keywords/struct.md), ya que todos los tipos de valor poseen implícitamente un constructor público predeterminado.  Es posible declarar constructores parametrizados en un tipo struct para establecer sus valores iniciales, pero sólo es necesario si se requieren valores distintos del predeterminado.  
  
 Los objetos de tipo valor, tales como los structs, se crean en la pila, mientras que los objetos de tipo referencia, tales como las clases, se crean en el montón.  Ambos tipos de objetos se destruyen automáticamente, pero los objetos basados en tipos de valor se destruyen cuando salen del ámbito, mientras que los objetos basados en tipos de referencia se destruyen en un momento no especificado después de quitar la última referencia a ellos.  En los tipos de referencia que consumen ciertos recursos, como grandes cantidades de memoria, identificadores de archivo o conexiones de red, a veces es conveniente emplear la finalización determinista para asegurarse de que el objeto se destruirá lo antes posible.  Para obtener más información, vea [using \(Instrucción\)](../../../csharp/language-reference/keywords/using-statement.md).  
  
 El operador `new` no se puede sobrecargar.  
  
 Si el operador `new` no puede asignar memoria, producirá la excepción <xref:System.OutOfMemoryException>.  
  
## Ejemplo  
 En el siguiente ejemplo, se crean e inicializan, mediante el operador `new`, un objeto `struct` y un objeto class y, a continuación, se les asignan valores.  Se muestran los valores predeterminados y asignados.  
  
 [!code-cs[csrefKeywordsOperator#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-operator_1.cs)]  
  
 Observe en el ejemplo que el valor predeterminado de una cadena es `null`.  Por lo tanto, no se muestra.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [new](../../../csharp/language-reference/keywords/new.md)   
 [Tipos anónimos](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)