---
title: this (Referencia de C#)
description: Palabra clave this (Referencia de C#)
keywords: this (C#), palabra clave this (C#), palabra clave this (Referencia de C#), palabra clave this (Referencia del lenguaje de C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1e764bbd85d06a3b1898f6574064b2844f6d6813
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="this-c-reference"></a>this (Referencia de C#)
La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.  
  
> [!NOTE]
>  En este artículo se describe el uso de `this` con instancias de clase. Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
 A continuación se indican usos habituales de `this`:  
  
-   Para calificar a miembros ocultos por nombres similares, por ejemplo:  
  
 [!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   Para pasar un objeto como parámetro a otros métodos, por ejemplo:  
  
    ```  
    CalcTax(this);  
    ```  
  
-   Para declarar indizadores, por ejemplo:  
  
 [!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto. Es un error hacer referencia a `this` en un método estático.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares. También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.  
  
 [!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [base](../../../csharp/language-reference/keywords/base.md)   
 [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md)

