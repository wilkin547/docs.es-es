---
title: "espacio de nombres (Referencia de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "namespace_CSharpKeyword"
  - "namespace"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "namespace (palabra clave) [C#]"
  - "ámbito [C#]"
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 28
---
# espacio de nombres (Referencia de C#)
La palabra clave `namespace` se utiliza para declarar un ámbito que contiene un conjunto de objetos relacionados.  Puede utilizar un espacio de nombres para organizar elementos de código y crear global \- tipos únicos.  
  
 [!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## Comentarios  
 Dentro de un espacio de nombres, se pueden declarar uno o varios de los siguientes tipos:  
  
-   otro espacio de nombres  
  
-   [clase](../../../csharp/language-reference/keywords/class.md)  
  
-   [interfaz](../../../csharp/language-reference/keywords/interface.md)  
  
-   [struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [enum](../../../csharp/language-reference/keywords/enum.md)  
  
-   [delegado](../../../csharp/language-reference/keywords/delegate.md)  
  
 Aunque declare explícitamente un espacio de nombres en un archivo de código fuente de C\#, el compilador agrega un espacio de nombres predeterminado.  Este espacio de nombres sin denominación, a veces se hace referencia a él como espacio de nombres global, está presente en todos los archivos.  Cualquier identificador del espacio de nombres global puede utilizarse también en un espacio de nombres declarado.  
  
 Los espacios de nombres disponen implícitamente de un acceso público que no puede modificarse.  Para obtener una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Un espacio de nombres se puede definir en dos o más declaraciones.  Por ejemplo, en el siguiente ejemplo se definen dos clases como parte del espacio de nombres `MyCompany`:  
  
 [!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## Ejemplo  
 El siguiente ejemplo muestra cómo realizar una llamada a un método estático en un espacio de nombres anidado.  
  
 [!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## Para obtener más información  
 Para obtener más información sobre el uso de espacios de nombres, vea los temas siguientes:  
  
-   [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C\#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [utilizar](../../../csharp/language-reference/keywords/using.md)