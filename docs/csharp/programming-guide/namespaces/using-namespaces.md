---
title: "Utilizar espacios de nombres (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.names"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nombres completos [C#]"
  - "espacios de nombres [C#], cómo se utiliza"
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
caps.latest.revision: 26
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 26
---
# Utilizar espacios de nombres (Gu&#237;a de programaci&#243;n de C#)
Los espacios de nombres se utilizan en gran medida en los programas de C\# de dos maneras.  Primero, las clases de .NET Framework utilizan los espacios de nombres para organizar sus diversas clases.  Segundo, declarar sus propios espacios de nombres permite ayudar a controlar el ámbito de la clase y los nombres de método en proyectos de programación de mayor tamaño.  
  
## Acceso a los espacios de nombres  
 La mayoría de las aplicaciones de C\# comienzan con una sección de directivas `using`.  Esta sección muestra los espacios de nombres que la aplicación utilizará con frecuencia y evita que el programador tenga que especificar un nombre completo cada vez que se utiliza un método contenido dentro.  
  
 Por ejemplo, incluyendo la línea:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 Al inicio de un programa, el programador puede utilizar el código:  
  
 [!code-cs[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#31)]  
  
 En lugar de:  
  
 [!code-cs[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/progGuide.cs#30)]  
  
## Alias de espacio de nombres  
 [using \(directiva\)](../../../csharp/language-reference/keywords/using-directive.md) también se puede utilizar para crear un alias para un [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md).  Por ejemplo, si utiliza un espacio de nombres escrito con anterioridad que contiene espacios de nombres anidados, puede declarar un alias para proporcionar una forma rápida de hacer referencia a uno en particular, tal y como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#7)]  
  
## Uso de espacios de nombres para controlar el ámbito  
 La palabra clave `namespace` se utiliza para declarar un ámbito.  La capacidad de crear ámbitos dentro del proyecto permite organizar el código y le permite crear tipos únicos globales.  En el ejemplo siguiente, una clase titulada `SampleClass` se define en dos espacios de nombres, uno anidado dentro de otro.  [Operador .](../../../csharp/language-reference/operators/member-access-operator.md) se utiliza para diferenciar a qué método se llama.  
  
 [!code-cs[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#8)]  
  
## Nombres completos  
 Los espacios de nombres y tipos tienen nombres únicos que se describen mediante nombres completos que indican una jerarquía lógica.  Por ejemplo, la instrucción `A.B` implica que `A` es el nombre del espacio de nombres o tipo y que `B` está anidado dentro de él.  
  
 En el siguiente ejemplo, se muestran clases y espacios de nombres anidados.  El nombre completo se indica como un comentario que sigue a cada entidad.  
  
 [!code-cs[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#9)]  
  
 En el segmento de código anterior:  
  
-   El espacio de nombres `N1` es un miembro del espacio de nombres global.  Su nombre completo es `N1`.  
  
-   El espacio de nombres `N2` es un miembro del espacio de nombres `N1`.  Su nombre completo es `N1.N2`.  
  
-   La clase `C1` es un miembro de `N1`.  Su nombre completo es `N1.C1`.  
  
-   El nombre de clase `C2` se utiliza dos veces en el código.  Sin embargo, los nombres completos son únicos.  La primera instancia de `C2` se declara dentro de `C1`; por lo tanto, su nombre completo es `N1.C1.C2`.  La segunda instancia de `C2` se declara dentro de un espacio de nombres `N2`; por lo tanto, su nombre completo es `N1.N2.C2`.  
  
 Mediante el segmento de código anterior, se puede agregar un nuevo miembro de clase, `C3`, al espacio de nombres `N1.N2` de la siguiente forma:  
  
 [!code-cs[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#10)]  
  
 En general, utilice `::` para hacer referencia a un alias de espacio de nombres o `global::` para hacer referencia al espacio de nombres global y `.` para calificar tipos o miembros.  
  
 No es correcto utilizar `::` con un alias que hace referencia a un tipo en lugar de a un espacio de nombres.  Por ejemplo:  
  
 [!code-cs[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#11)]  
  
 [!code-cs[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#12)]  
  
 Recuerde que la palabra `global` no es un alias predefinido; por lo tanto, `global.X` no tiene ningún significado especial.  Sólo adquiere un significado especial si se utiliza con `::`.  
  
 La advertencia del compilador CS0440 se genera si se define un alias denominado global porque `global::` siempre hace referencia al espacio de nombres global y no a un alias.  Por ejemplo, la línea siguiente genera la advertencia:  
  
 [!code-cs[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces2.cs#13)]  
  
 El uso de `::` con alias es una buena idea y proporciona protección contra la introducción inesperada de tipos adicionales.  Por ejemplo, considere este ejemplo:  
  
 [!code-cs[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#14)]  
  
 [!code-cs[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#15)]  
  
 Esto funciona, pero si después se introdujera un tipo denominado `Alias`, `Alias.` se enlazaría en su lugar a ese tipo.  El uso de `Alias::Exception` asegura que `Alias` se trate como un alias de espacio de nombres y no se confunda con un tipo.  
  
 Consulte el tema [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) para obtener más información sobre el alias `global`.  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Operador .](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: \(operador\)](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)