---
title: Espacios de nombres (Guía de programación de C#)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c5431e5141b1b4b1981f4a1399ca11939fe7dc45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151121"
---
# <a name="namespaces-c-programming-guide"></a>Espacios de nombres (Guía de programación de C#)

Los espacios de nombres se usan mucho en programación de C# de dos maneras. En primer lugar, .NET Framework usa espacios de nombres para organizar sus clases, de la siguiente manera:  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` es un espacio de nombres y `Console` es una clase de ese espacio de nombres. La palabra clave `using` se puede usar para que no se necesite el nombre completo, como en el ejemplo siguiente:  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
Para más información, vea [using (Directiva)](../../language-reference/keywords/using-directive.md).  
  
En segundo lugar, declarar sus propios espacios de nombres puede ayudarle a controlar el ámbito de nombres de clase y método en proyectos de programación grandes. Use la palabra clave [namespace](../../language-reference/keywords/namespace.md) para declarar un espacio de nombres, como en el ejemplo siguiente:  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

El nombre del espacio de nombres debe ser un [nombre de identificador](../inside-a-program/identifier-names.md) de C# válido.

## <a name="namespaces-overview"></a>Información general sobre los espacios de nombres  

Los espacios de nombres tienen las propiedades siguientes:  
  
- Organizan proyectos de código de gran tamaño.  
- Se delimitan mediante el operador `.`.  
- La directiva `using` obvia la necesidad de especificar el nombre del espacio de nombres para cada clase.  
- El espacio de nombres `global` es el espacio de nombres "raíz": `global::System` siempre hará referencia al espacio de nombres <xref:System> de .NET.  

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Utilizar espacios de nombres](using-namespaces.md)
- [Cómo: Utilizar el alias del espacio de nombres global](how-to-use-the-global-namespace-alias.md)
- [Cómo: Utilizar el espacio de nombres My](how-to-use-the-my-namespace.md)
- [Guía de programación de C#](../index.md)  
- [Nombres de identificador](../inside-a-program/identifier-names.md)
- [Palabras clave del espacio de nombres](../../language-reference/keywords/namespace-keywords.md)  
- [using (directiva)](../../language-reference/keywords/using-directive.md)  
- [Operador ::](../../language-reference/operators/namespace-alias-qualifer.md)  
- [. !](../../language-reference/operators/member-access-operator.md)
