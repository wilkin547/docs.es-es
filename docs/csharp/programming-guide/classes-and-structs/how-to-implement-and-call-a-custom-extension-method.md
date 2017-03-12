---
title: "C&#243;mo: Implementar e invocar un m&#233;todo de extensi&#243;n personalizado (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "métodos de extensión [C#], implementar y llamar"
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Implementar e invocar un m&#233;todo de extensi&#243;n personalizado (Gu&#237;a de programaci&#243;n de C#)
En este tema se muestra cómo implementar dispone los métodos de extensión para el tipo en [biblioteca de clases de .NET Framework.](http://go.microsoft.com/fwlink/?LinkID=217856), o cualquier otro tipo .NET que desea extender.  El código cliente puede utilizar sus métodos de extensión agregando una referencia al archivo DLL que los contiene, así como una directiva [using](../../../csharp/language-reference/keywords/using-directive.md) que especifica el espacio de nombres en el que se definen los métodos de extensión.  
  
### Para definir y llamar al método de extensión  
  
1.  Defina una [clase](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) estática que contenga el método de extensión.  
  
     La clase debe estar visible para el código cliente.  Para obtener más información sobre las reglas de accesibilidad, vea [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Implemente el método de extensión como método estático que tenga al menos la misma visibilidad que la clase contenedora.  
  
3.  El primer parámetro del método especifica el tipo en el que funciona el método; debe estar precedido del modificador [this](../../../csharp/language-reference/keywords/this.md).  
  
4.  En el código de llamada, agregue una directiva `using` para especificar el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) que contiene la clase del método de extensión.  
  
5.  Llame a los métodos como si fueran métodos de instancia en el tipo.  
  
     Observe que el código de llamada no especifica el primer parámetro porque éste representa el tipo en el que se aplica el operador y el compilador ya conoce el tipo del objeto.  Sólo tiene que proporcionar argumentos para segundos parámetros a través de `n`.  
  
## Ejemplo  
 En el ejemplo siguiente se implementa un método de extensión denominado `WordCount` en la clase `CustomExtensions.StringExtension`.  El método funciona en la clase <xref:System.String>, que se especifica como primer parámetro de método.  El espacio de nombres `CustomExtensions` se importa al espacio de nombres de la aplicación y se llama al método desde el método `Main`.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/how-to-implement-and-cal_1.cs)]  
  
## Compilar el código  
 Para ejecutar este código, debe copiarlo y pegarlo en un proyecto de aplicación de consola de Visual C\# creado en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva `using` para System.Linq.  Si el proyecto no cumple uno o varios de estos requisitos, puede agregar lo que falte manualmente.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Seguridad de .NET Framework  
 Los métodos de extensión no presentan vulnerabilidades de seguridad concretas.  No se pueden utilizar para suplantar los métodos existentes en un tipo, ya que todas las colisiones de nombre se resuelven a favor de la instancia o el método estático definido por el propio tipo.  Los métodos de extensión no pueden obtener acceso a los datos privados de la clase extendida.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md)