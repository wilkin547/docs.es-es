---
title: "Constantes (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, constantes"
  - "constantes [C#]"
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# Constantes (Gu&#237;a de programaci&#243;n de C#)
Las constantes son valores inmutables que se conocen en tiempo de compilación y no cambian mientras dura el programa.  Las constantes se declaran con el modificador [const](../../../csharp/language-reference/keywords/const.md).  Solo los tipos integrados de C\# \(excluido <xref:System.Object?displayProperty=fullName>\) se pueden declarar como `const`.  Para obtener una lista de los tipos integrados, vea [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md).  Los tipos definidos por el usuario, incluidas las clases, los structs y las matrices, no pueden ser `const`.  Use el modificador [readonly](../../../csharp/language-reference/keywords/readonly.md) para crear una clase, un struct o una matriz que se inicialice una vez en tiempo de ejecución \(por ejemplo, en un constructor\) y que posteriormente no se pueda cambiar.  
  
 C\# no admite los métodos, propiedades o eventos `const`.  
  
 El tipo de enumeración permite definir constantes con nombre para los tipos integrados enteros \(por ejemplo `int`, `uint`, `long`, etc.\).  Para obtener más información, consulte [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Las constantes se deben inicializar tal como se declaran.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/constants_1.cs)]  
  
 En este ejemplo, la constante `months` siempre es 12 y no se puede cambiar, ni siquiera puede hacerlo la propia clase.  De hecho, cuando el compilador encuentra un identificador de constante en el código fuente de C\# \(por ejemplo, `months`\), sustituye directamente el valor literal en el código de lenguaje intermedio \(IL\) que genera.  Dado que no hay ninguna dirección de variable asociada a una constante en tiempo de ejecución, los campos `const` no se pueden pasar mediante referencia y no pueden aparecer como un valor de l en una expresión.  
  
> [!NOTE]
>  Actúe con precaución al hacer referencia a los valores constantes definidos en otro código como los archivos DLL.  Si una nueva versión del archivo DLL define un nuevo valor para la constante, el programa conservará el valor literal anterior hasta que se vuelva a compilar con la nueva versión.  
  
 Se pueden declarar varias constantes del mismo tipo al mismo tiempo, por ejemplo:  
  
 [!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/constants_2.cs)]  
  
 La expresión utilizada para inicializar una constante puede hacer referencia a otra constante si no crea una referencia circular.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/constants_3.cs)]  
  
 Las constantes se pueden marcar como [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected``internal`.  Estos modificadores de acceso definen cómo los usuarios de la clase pueden tener acceso a la constante.  Para obtener más información, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 El acceso a las constantes se realiza como si éstas fuesen campos [estáticos](../../../csharp/language-reference/keywords/static.md), porque el valor de la constante es el mismo en todas las instancias del tipo.  No se utiliza la palabra clave `static` para declararlas.  Las expresiones que no están incluidas en la clase que define la constante deben usar el nombre de la clase, un punto y el nombre de la constante para tener acceso a la constante.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/constants_4.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)   
 [Tipos](../../../csharp/programming-guide/types/index.md)   
 [readonly](../../../csharp/language-reference/keywords/readonly.md)   
 [Immutability in C\# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)