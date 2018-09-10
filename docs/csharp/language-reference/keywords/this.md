---
title: this (Referencia de C#)
description: Palabra clave this (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
ms.openlocfilehash: df1bf6a3e6d24b231bf5e3c7a960f49084c4e53a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185066"
---
# <a name="this-c-reference"></a>this (Referencia de C#)
La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.  
  
> [!NOTE]
>  En este artículo se describe el uso de `this` con instancias de clase. Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 A continuación se indican usos habituales de `this`:  
  
-   Para calificar a miembros ocultos por nombres similares, por ejemplo:  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Para pasar un objeto como parámetro a otros métodos, por ejemplo:  
  
    ```csharp  
    CalcTax(this);  
    ```  
  
-   Para declarar indizadores, por ejemplo:  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto. Es un error hacer referencia a `this` en un método estático.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares. También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
- [base](../../../csharp/language-reference/keywords/base.md)  
- [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)
