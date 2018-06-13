---
title: espacio de nombres (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 343cce85dd235532fbe3fc90af0a785f48518db7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276024"
---
# <a name="namespace-c-reference"></a>espacio de nombres (Referencia de C#)
La palabra clave `namespace` se usa para declarar un ámbito que contiene un conjunto de objetos relacionados. Puede usar un espacio de nombres para organizar los elementos de código y crear tipos únicos globales.  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a>Comentarios  
 En un espacio de nombres, se pueden declarar uno o varios de los siguientes tipos:  
  
-   otro espacio de nombres  
  
-   [class](../../../csharp/language-reference/keywords/class.md)  
  
-   [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   [struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [enum](../../../csharp/language-reference/keywords/enum.md)  
  
-   [delegate](../../../csharp/language-reference/keywords/delegate.md)  
  
 Tanto si se declara explícitamente un espacio de nombres en un archivo de código fuente de C# como si no, el compilador agrega un espacio de nombres predeterminado. Este espacio de nombres sin nombre, que a veces se denomina espacio de nombres global, está presente en todos los archivos. Todos los identificadores del espacio de nombres global están disponibles para su uso en un espacio de nombres con nombre.  
  
 Los espacios de nombres tienen implícitamente acceso público y esto no se puede modificar. Para ver una descripción de los modificadores de acceso que se pueden asignar a los elementos de un espacio de nombres, vea [Modificadores de acceso](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Es posible definir un espacio de nombres en dos o más declaraciones. Por ejemplo, en el ejemplo siguiente se definen dos clases como parte del espacio de nombres `MyCompany`:  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo llamar a un método estático en un espacio de nombres anidado.  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a>Para obtener más información  
 Para obtener más información sobre el uso de los espacios de nombres, vea los temas siguientes:  
  
-   [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [using](../../../csharp/language-reference/keywords/using.md)
