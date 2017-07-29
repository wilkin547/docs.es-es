---
title: "using (Instrucción, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 201dde951b4f92d92b7d78b3d71a3f3cfb559507
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-statement-c-reference"></a>using (Instrucción, Referencia de C#)
Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la instrucción using.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Comentarios  
 <xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo). Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan. Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.  
  
 Como regla general, cuando se usa un objeto `IDisposable`, debe declarar y crear instancias del mismo en una instrucción `using`. La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>. Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar.  
  
 La instrucción `using` garantiza que se llama a <xref:System.IDisposable.Dispose%2A> aunque se produzca una excepción mientras llama a métodos en el objeto. Puede lograr el mismo resultado colocando el objeto dentro de un bloque try y llamando luego a <xref:System.IDisposable.Dispose%2A> en un bloque finally; de hecho, es así cómo el compilador traduce la instrucción `using`. El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 Se pueden declarar varias instancias de un tipo en una instrucción `using`, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado. En este caso, el objeto permanece en el ámbito después de que el control abandone el bloque `using` aunque probablemente ya no tenga acceso a sus recursos no administrados. En otras palabras, ya no estará completamente inicializado. Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción. Por este motivo, suele ser mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [using Directive](../../../csharp/language-reference/keywords/using-directive.md)  (using [Directiva, Referencia de C#])  
 [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)   
 [Implementar un método Dispose](../../../standard/garbage-collection/implementing-dispose.md)

