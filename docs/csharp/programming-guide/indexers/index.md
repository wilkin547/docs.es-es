---
title: "Indizadores (Guía de programación de C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="indexers-c-programming-guide"></a>Indizadores (Guía de programación de C#)

Los indizadores permiten indizar las instancias de una clase o struct como matrices. El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia. Son similares a [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.  
 
 En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) sencillos para asignar y recuperar valores. La clase `Program` crea una instancia de esta clase para almacenar cadenas.  
  
 [!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  Para obtener más ejemplos, vea [Secciones relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Definiciones de cuerpos de expresión  
 
Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor. Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario. A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.

[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza. 

A partir de C# 7, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión. En este caso, sí deben utilizarse las palabras clave `get` y `set`. Por ejemplo:

[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Información general sobre los indizadores  
  
-   Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.  
  
-   Un descriptor de acceso `get` devuelve un valor. Un descriptor de acceso `set` asigna un valor.  
  
-   La palabra clave [this](../../../csharp/language-reference/keywords/this.md) se usa para definir los indizadores.  
  
-   La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.  
  
-   Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.  
  
-   Los indizadores se pueden sobrecargar.  
  
-   Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.  
  
##  <a name="BKMK_RelatedSections"></a> Secciones relacionadas  
  
-   [Utilizar indizadores](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Indizadores en Interfaces](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Comparación entre propiedades e indizadores](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Restringir la accesibilidad del descriptor de acceso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md)

