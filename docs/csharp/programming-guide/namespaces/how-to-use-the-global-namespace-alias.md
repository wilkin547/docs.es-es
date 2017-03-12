---
title: "C&#243;mo: Utilizar el alias del espacio de nombres global (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "alias [C#]"
  - "global (espacio de nombres) [C#]"
  - "espacios de nombres [C#], calificador de espacio de nombres global"
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# C&#243;mo: Utilizar el alias del espacio de nombres global (Gu&#237;a de programaci&#243;n de C#)
Es útil poder tener acceso a un miembro en el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) global cuando otra entidad con el mismo nombre puede ocultar el miembro.  
  
 Por ejemplo, en el siguiente código, `Console` tiene como resultado `TestApp.Console` en lugar del tipo `Console` del espacio de nombres <xref:System>.  
  
 [!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/csharp/csProgGuide/using.cs#1)]  
  
 [!code-cs[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#1)]  
  
 La utilización de `System.Console` aún produce un error porque la clase `TestApp.System` oculta el espacio de nombres `System`:  
  
 [!code-cs[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#2)]  
  
 Sin embargo, este error se puede evitar utilizando `global::System.Console`, del modo siguiente:  
  
 [!code-cs[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#3)]  
  
 Cuando el identificador izquierdo es `global`, la búsqueda del identificador derecho se inicia en el espacio de nombres global.  Por ejemplo, la siguiente declaración hace referencia a `TestApp` como miembro del espacio global.  
  
 [!code-cs[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#4)]  
  
 Obviamente, no se recomienda la creación de espacios de nombres propios denominados `System` y es improbable que se encuentre algún código en el que se haya hecho esto.  Sin embargo, en proyectos grandes, es muy posible que se pueda producir la duplicación del espacio de nombres en un formulario u otro.  En estas situaciones, el calificador de espacio de nombres global es la garantía de que se puede especificar el espacio de nombres raíz.  
  
## Ejemplo  
 En este ejemplo, se utiliza el espacio de nombres `System` para incluir la clase `TestClass`; por lo tanto, se debe utilizar `global::System.Console` para hacer referencia a la clase `System.Console`, que el espacio de nombres `System` oculta.  Además, el alias `colAlias` se utiliza para hacer referencia al espacio de nombres `System.Collections`; por consiguiente, la instancia de un objeto <xref:System.Collections.Hashtable?displayProperty=fullName> se crea con este alias en lugar del espacio de nombres.  
  
 [!code-cs[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces.cs#5)]  
  
  **A 1**  
**B 2**  
**C 3**   
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)   
 [Operador .](../../../csharp/language-reference/operators/member-access-operator.md)   
 [:: \(operador\)](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [extern](../../../csharp/language-reference/keywords/extern.md)