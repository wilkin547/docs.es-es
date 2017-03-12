---
title: "Constructores privados (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, constructores privados"
  - "private (constructores) [C#]"
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Constructores privados (Gu&#237;a de programaci&#243;n de C#)
Un constructor private es un caso especial de constructor de instancia.  Se utiliza generalmente en clases que contienen sólo miembros estáticos.  Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases \(excepto las anidadas\) no podrán crear instancias de esta clase.  Por ejemplo:  
  
 [!code-cs[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/private-constructors_1.cs)]  
  
 La declaración de un constructor vacío evita la generación automática de un constructor predeterminado.  Observe que si no utiliza un modificador de acceso en el constructor, éste será private de manera predeterminada.  Sin embargo, normalmente se utiliza el modificador [private](../../../csharp/language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.  
  
 Los constructores privados se utilizan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase.  Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática.  Para obtener más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
## Ejemplo  
 El siguiente es un ejemplo de clase que utiliza un constructor private.  
  
 [!code-cs[csProgGuideObjects#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/private-constructors_2.cs)]  
  
 Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:  
  
 [!code-cs[csProgGuideObjects#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/private-constructors_3.cs)]  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Destructores](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [public](../../../csharp/language-reference/keywords/public.md)