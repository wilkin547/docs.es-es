---
title: "C&#243;mo: Inicializar objetos usando un inicializador de objeto (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "inicializadores de objeto [C#], cómo se utiliza"
  - "objetos [C#], inicializar"
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# C&#243;mo: Inicializar objetos usando un inicializador de objeto (Gu&#237;a de programaci&#243;n de C#)
Puede usar inicializadores de objetos para inicializar objetos de tipo de forma declarativa sin tener que invocar explícitamente a un constructor del tipo.  
  
 En los ejemplos siguientes se muestra cómo utilizar inicializadores de objeto con objetos con nombre.  El compilador procesa los inicializadores de objeto accediendo primero al constructor predeterminado de la instancia y luego procesa las inicializaciones de miembro.  Por consiguiente, si el constructor predeterminado se declara como `private` en la clase, se producirán errores en los inicializadores de objeto que requieran acceso público.  
  
 Debe utilizar un inicializador de objeto si define un tipo anónimo.  Para obtener más información, vea [Cómo: Devolver subconjuntos de propiedades de elementos en una consulta](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo inicializar un tipo `StudentName` nuevo mediante inicializadores de objeto.  
  
 [!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo inicializar una colección de tipos `StudentName` mediante un inicializador de colección.  Observe que un inicializador de colección es una serie de inicializadores de objeto separados por comas.  
  
 [!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## Compilar el código  
 Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C\# creado en [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)