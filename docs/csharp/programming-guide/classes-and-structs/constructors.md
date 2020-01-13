---
title: 'Constructores: Guía de programación de C#'
ms.date: 05/05/2017
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
ms.openlocfilehash: 9c57ff6dd9acd8a8bcff6de4fce7d898f1135703
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714966"
---
# <a name="constructors-c-programming-guide"></a>Constructores (Guía de programación de C#)

Cada vez que se crea una [clase](../../language-reference/keywords/class.md) o [struct](../../language-reference/keywords/struct.md), se llama a su constructor. Una clase o struct puede tener varios constructores que toman argumentos diferentes. Los constructores permiten al programador establecer valores predeterminados, limitar la creación de instancias y escribir código flexible y fácil de leer. Para obtener más información y ejemplos, vea [Usar constructores](./using-constructors.md) y [Constructores de instancias](./instance-constructors.md).  

## <a name="parameterless-constructors"></a>Constructores sin parámetros
  
Si no proporciona un constructor para la clase, C# creará uno de manera predeterminada que cree instancias del objeto y establezca las variables miembro en los valores predeterminados que se indican en [Tabla de valores predeterminados](../../language-reference/keywords/default-values-table.md). Si no proporciona un constructor para su struct, C# se basa en un *constructor sin parámetros implícito* para inicializar automáticamente cada campo de un tipo de valor en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../language-reference/keywords/default-values-table.md). Para obtener más información y ejemplos, vea [Constructores de instancias](./instance-constructors.md).  

## <a name="constructor-syntax"></a>Sintaxis del constructor

Un constructor es un método cuyo nombre es igual que el nombre de su tipo. Su firma del método incluye solo el nombre del método y su lista de parámetros; no incluye un tipo de valor devuelto. En el ejemplo siguiente se muestra el constructor de una clase denominada `Person`.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Si un constructor puede implementarse como una instrucción única, puede usar una [definición del cuerpo de expresión](../statements-expressions-operators/expression-bodied-members.md). En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*. La definición del cuerpo de expresión asigna el argumento al campo `locationName`.

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Constructores estáticos

En los ejemplos anteriores se han mostrado constructores de instancia, que crean un objeto nuevo. Una clase o struct también puede tener un constructor estático, que inicializa los miembros estáticos del tipo.  Los constructores estáticos no tienen parámetros. Si no proporciona un constructor estático para inicializar los campos estáticos, el compilador de C# inicializa los campos estáticos en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../language-reference/keywords/default-values-table.md).

En el ejemplo siguiente se usa un constructor estático para inicializar un campo estático.

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

También puede definir un constructor estático con una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente. 

[!code-csharp[constructors](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Para obtener más información y ejemplos, vea [Constructores estáticos](./static-constructors.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Utilizar constructores](./using-constructors.md)  
  
 [Constructores de instancias](./instance-constructors.md)  
  
 [Constructores privados](./private-constructors.md)  
  
 [Constructores estáticos](./static-constructors.md)  
  
 [Escritura de un constructor de copia](./how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Finalizadores](./destructors.md)
- [static](../../language-reference/keywords/static.md)
- [Why Do Initializers Run In The Opposite Order As Constructors? Part One](https://blogs.msdn.microsoft.com/ericlippert/2008/02/15/why-do-initializers-run-in-the-opposite-order-as-constructors-part-one) (¿Por qué los inicializadores se ejecutan en orden contrario a los constructores? Parte uno)
