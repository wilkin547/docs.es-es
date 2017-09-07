---
title: "Constructores (Guía de programación de C#)"
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="constructors-c-programming-guide"></a>Constructores (Guía de programación de C#)
Cada vez que se crea una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), se llama a su constructor. Una clase o struct puede tener varios constructores que toman argumentos diferentes. Los constructores permiten al programador establecer valores predeterminados, limitar la creación de instancias y escribir código flexible y fácil de leer. Para obtener más información y ejemplos, vea [Usar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) y [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="default-constructors"></a>Constructores predeterminados
  
Si no proporciona un constructor para la clase, C# creará uno de manera predeterminada que cree instancias del objeto y establezca las variables miembro en los valores predeterminados que se indican en [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md). Si no proporciona un constructor para su struct, C# se basa en un *constructor predeterminado implícito* para inicializar automáticamente cada campo de un tipo de valor en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md). Para obtener más información y ejemplos, vea [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  

## <a name="constructor-syntax"></a>Sintaxis del constructor

Un constructor es un método cuyo nombre es igual que el nombre de su tipo. Su firma del método incluye solo el nombre del método y su lista de parámetros; no incluye un tipo de valor devuelto. En el ejemplo siguiente se muestra el constructor de una clase denominada `Person`.

[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

Si un constructor puede implementarse como una instrucción única, puede usar una [definición del cuerpo de expresión](../statements-expressions-operators/expression-bodied-members.md). En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*. La definición del cuerpo de expresión asigna el argumento al campo `locationName`.

[!code-cs[constructor con cuerpo de expresión](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>Constructores estáticos

En los ejemplos anteriores se han mostrado constructores de instancia, que crean un objeto nuevo. Una clase o struct también puede tener un constructor estático, que inicializa los miembros estáticos del tipo.  Los constructores estáticos no tienen parámetros. Si no proporciona un constructor estático para inicializar los campos estáticos, el compilador de C# proporcionará un constructor estático predeterminado que inicializa los campos estáticos en su valor predeterminado como se muestra en la [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md). 

En el ejemplo siguiente se usa un constructor estático para inicializar un campo estático.

[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

También puede definir un constructor estático con una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente. 

[!code-cs[constructores](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

Para obtener más información y ejemplos, vea [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="in-this-section"></a>En esta sección  
 [Utilizar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [Constructores de instancias](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [Constructores privados](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [Constructores estáticos](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [Cómo: Escribir un constructor Copy](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [Why Do Initializers Run In The Opposite Order As Constructors? Part One](http://go.microsoft.com/fwlink/?LinkId=112374) (¿Por qué los inicializadores se ejecutan en orden contrario a los constructores? Parte uno)

