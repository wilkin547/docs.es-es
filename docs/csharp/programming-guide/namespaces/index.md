---
title: "Espacios de nombres (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, espacios de nombres"
  - "espacios de nombres [C#]"
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# Espacios de nombres (Gu&#237;a de programaci&#243;n de C#)
Los espacios de nombres se utilizan en gran medida en la programación de C\# de dos maneras.  En primer lugar, .NET Framework utiliza los espacios de nombres para organizar sus múltiples clases, de la forma siguiente:  
  
 [!code-cs[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` es un espacio de nombres y `Console` es una clase de ese espacio de nombres.  Se puede utilizar la palabra clave `using` para que no se requiera el nombre completo, como en el ejemplo siguiente:  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-cs[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 Para obtener más información, vea [using \(directiva\)](../../../csharp/language-reference/keywords/using-directive.md).  
  
 En segundo lugar, declarar espacios de nombres propios puede ayudar a controlar el ámbito de clase y nombres de método en proyectos de programación grandes.  Utilice la palabra clave [namespace](../../../csharp/language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## Información general sobre los espacios de nombres  
 Los espacios de nombres tienen las propiedades siguientes:  
  
-   Organizan proyectos de código de gran tamaño.  
  
-   El operador `.` delimita los espacios de nombres.  
  
-   `using directive` hace que no sea necesario especificar el nombre del espacio de nombres para cada clase.  
  
-   El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres `System` de .NET Framework.  
  
## Secciones relacionadas  
 Para obtener más información acerca de los espacios de nombres, consulte los temas siguientes:  
  
-   [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Cómo: Utilizar el espacio de nombres My](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using \(directiva\)](../../../csharp/language-reference/keywords/using-directive.md)   
 [:: \(operador\)](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [Operador .](../../../csharp/language-reference/operators/member-access-operator.md)