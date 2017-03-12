---
title: "C&#243;mo: Inicializar un diccionario con un inicializador de colecci&#243;n (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "inicializadores de colección [C#], con diccionario"
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# C&#243;mo: Inicializar un diccionario con un inicializador de colecci&#243;n (Gu&#237;a de programaci&#243;n de C#)
<xref:System.Collections.Generic.Dictionary%602> contiene una colección de pares clave\/valor.  Su método <xref:System.Collections.Generic.Dictionary%602.Add%2A> acepta dos parámetros, uno para la clave y otro para el valor.  Para inicializar <xref:System.Collections.Generic.Dictionary%602> o cualquier colección cuyo método `Add` acepte varios parámetros, encierre entre corchetes cada uno de los conjuntos de parámetros, como se muestra en el ejemplo siguiente.  
  
## Ejemplo  
 En el ejemplo de código siguiente, <xref:System.Collections.Generic.Dictionary%602> se inicializa con instancias de tipo `StudentName`.  
  
 [!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#34)]  
  
 Observe los dos pares de llaves en cada elemento de la colección.  Las llaves internas contienen el inicializador de objeto para `StudentName` y las llaves externas contienen el inicializador para el par clave\-valor que se agregará a `students`<xref:System.Collections.Generic.Dictionary%602>.  Por último, se escribe entre llaves todo el inicializador de colección del diccionario.  
  
## Compilar el código  
 Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C\# creado en [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)].  De manera predeterminada, el proyecto tiene como destino la versión 3.5 de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] y contiene una referencia a System.Core.dll y una directiva using para System.Linq.  Si el proyecto no cumple uno o varios de estos requisitos, puede agregar lo que falte manualmente.  Para obtener más información, vea [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md).  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Inicializadores de objeto y colección](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)