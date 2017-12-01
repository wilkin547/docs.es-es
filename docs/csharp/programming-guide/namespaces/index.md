---
title: "Espacios de nombres (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3eb645f5beb61d3cec97a70a54e660c65be52091
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-c-programming-guide"></a>Espacios de nombres (Guía de programación de C#)
Los espacios de nombres se usan mucho en programación de C# de dos maneras. En primer lugar, .NET Framework usa espacios de nombres para organizar sus clases, de la siguiente manera:  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` es un espacio de nombres y `Console` es una clase de ese espacio de nombres. La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 Para obtener más información, consulte [using (Directiva)](../../../csharp/language-reference/keywords/using-directive.md).  
  
 En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes. Use la palabra clave [namespace](../../../csharp/language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a>Información general sobre los espacios de nombres  
 Los espacios de nombres tienen las propiedades siguientes:  
  
-   Organizan proyectos de código de gran tamaño.  
  
-   Se delimitan mediante el operador `.`.  
  
-   `using directive` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.  
  
-   El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres `System` de .NET Framework.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 Vea los siguientes temas para obtener más información sobre los espacios de nombres:  
  
-   [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [Cómo: Utilizar el espacio de nombres My](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [using (directiva)](../../../csharp/language-reference/keywords/using-directive.md)  
 [Operador ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [. !](../../../csharp/language-reference/operators/member-access-operator.md)
