---
title: "Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2a854d2f963578cb8b89da445af660f3c029fae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>Cómo: Utilizar el alias del espacio de nombres global (Guía de programación de C#)
La capacidad de tener acceso a un miembro en el [espacio de nombres](../../../csharp/language-reference/keywords/namespace.md) global es útil cuando el miembro puede estar oculto por otra entidad del mismo nombre.  
  
 Por ejemplo, en el código siguiente, `Console` se resuelve como `TestApp.Console` en lugar de como el tipo `Console` en el espacio de nombres <xref:System>.  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 Usar `System.Console` todavía provoca un error porque el espacio de nombres `System` está oculto mediante la clase `TestApp.System`:  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 En cambio, puede solucionar este error con `global::System.Console`, como se muestra aquí:  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 Cuando el identificador izquierdo es `global`, la búsqueda del identificador derecho comienza en el espacio de nombres global. Por ejemplo, la siguiente declaración está haciendo referencia a `TestApp` como un miembro del espacio global.  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 Obviamente, no se recomienda crear sus propios espacios de nombres denominados `System`, y es poco probable que encuentre cualquier código donde haya ocurrido esto. En cambio, en proyectos más grandes, es una posibilidad muy real que pueda producirse una duplicación de espacio de nombres de una forma u otra. En estas situaciones, el calificador de espacio de nombres global es su garantía de que puede especificar el espacio de nombres raíz.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, el espacio de nombres `System` se usa para incluir la clase `TestClass`, por lo tanto, `global::System.Console` debe usarse para hacer referencia a la clase `System.Console`, que está oculta por el espacio de nombres `System`. Además, el alias `colAlias` se usa para hacer referencia al espacio de nombres `System.Collections`; por lo tanto, la instancia de <xref:System.Collections.Hashtable?displayProperty=nameWithType> se ha creado con este alias en lugar del espacio de nombres.  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
 **A 1**  
**B 2**  
**C 3**   
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)  
 [. .](../../../csharp/language-reference/operators/member-access-operator.md)  
 [Operador ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [extern](../../../csharp/language-reference/keywords/extern.md)
