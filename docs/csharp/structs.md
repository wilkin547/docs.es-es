---
title: 'Structs: Guía de C#'
description: Obtenga información sobre el tipo struct y cómo se crea.
ms.date: 10/12/2016
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: fbaa7fcc26009fe3117784b411941d30af0ba3c5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608019"
---
# <a name="structs"></a>Estructuras
Un *struct* es un tipo de valor. Cuando se crea un struct, la variable a la que se asigna el struct contiene los datos reales del struct. Cuando la estructura se asigna a una nueva variable, se copia. Por lo tanto, la nueva variable y la variable original contienen dos copias independientes de los mismos datos. Los cambios realizados en una copia no afectan a la otra copia.

Las variables de tipo de valor contienen directamente sus valores, lo que significa que la memoria se asigna insertada en cualquier contexto en el que se declare la variable. No se produce ninguna asignación del montón independiente ni sobrecarga de la recolección de elementos no utilizados para las variables de tipo de valor.  
  
Existen dos categorías de tipos de valor: [struct](./language-reference/keywords/struct.md) y [enum](./language-reference/keywords/enum.md).  
  
Los tipos numéricos integrados son structs y tienen propiedades y métodos a los que se puede obtener acceso:  
  
[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]
  
Pero se declaran y se les asignan valores como si fueran tipos simples no agregados:  
  
[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)] 
  
Los tipos de valor están *sellados*, lo que significa que, por ejemplo, no puede derivar un tipo de <xref:System.Int32>, y no puede definir un struct para que herede de cualquier clase o struct definido por el usuario, porque un struct solo puede heredar de <xref:System.ValueType>. A pesar de ello, un struct puede implementar una o más interfaces. Puede convertir un tipo struct en un tipo de interfaz. Esto hace que una operación de conversión *boxing* encapsule el struct dentro de un objeto de tipo de referencia en el montón administrado. Las operaciones de conversión boxing se producen cuando se pasa un tipo de valor a un método que toma <xref:System.Object> como parámetro de entrada. Para obtener más información, vea [Conversión boxing y unboxing](./programming-guide/types/boxing-and-unboxing.md ).  
  
Puede usar la palabra clave [struct](./language-reference/keywords/struct.md) para crear sus propios tipos de valor personalizados. Normalmente, un struct se usa como un contenedor para un pequeño conjunto de variables relacionadas, como se muestra en el ejemplo siguiente:  
  
[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]  
  
Para obtener más información sobre los tipos de valor de .NET Framework, vea [Sistema de tipos comunes](../standard/common-type-system.md).  
    
Los structs comparten la mayoría de la sintaxis con las clases, aunque están más limitados que estas:  
  
- Dentro de una declaración de struct, los campos no se pueden inicializar a menos que se declaren como `const` o `static`.  
  
- Un struct no puede declarar un constructor sin parámetros ni un finalizador.  
  
- Los structs se copian en la asignación. Cuando se asigna un struct a una variable nueva, se copian todos los datos y las modificaciones que se realicen en la nueva copia no cambiarán los datos de la copia original. Es importante que lo recuerde al trabajar con colecciones de tipos de valor como Dictionary<string, myStruct>.  
  
- Los structs son tipos de valor y las clases son tipos de referencia.  
  
- A diferencia de las clases, se pueden crear instancias de structs sin usar un operador `new`.  
  
- Los structs pueden declarar constructores que tengan parámetros.  
  
- Así, un struct no puede heredar de otra clase o de otro struct, como tampoco puede ser la base de una clase. Todos los structs heredan directamente de <xref:System.ValueType>, que hereda de <xref:System.Object>.  
  
- Un struct puede implementar interfaces.

## <a name="literal-values"></a>Valores literales  
En C#, los valores literales reciben un tipo del compilador. Puede especificar cómo debe escribirse un literal numérico; para ello, anexe una letra al final del número. Por ejemplo, para especificar que el valor 4.56 debe tratarse como un valor flotante, anexe "f" o "F" después del número: `4.56f`. Si no se anexa ninguna letra, el compilador inferirá el tipo `double` para el literal. Para obtener más información sobre los tipos que se pueden especificar con sufijos de letras, vea las páginas de referencia de los tipos individuales en [Tipos de valor](./language-reference/keywords/value-types.md).  
  
Dado que los literales tienen tipo y todos los tipos derivan en última instancia de <xref:System.Object>, puede escribir y compilar código como el siguiente:  
  
[!code-csharp[Literal Values](../../samples/snippets/csharp/concepts/structs/literals.cs)]

En los dos últimos ejemplos se muestran las características del lenguaje incluidas en C# 7.0. El primero permite usar caracteres de subrayado como *separadores de dígitos* dentro de literales numéricos. Puede colocarlos donde quiera entre los dígitos para mejorar la legibilidad. No tienen ningún efecto en el valor.

En el segundo se muestran *literales binarios*, que permiten especificar patrones de bits directamente, en lugar de mediante la notación hexadecimal.

## <a name="nullable-types"></a>Tipos que aceptan valores NULL  
Los tipos de valor normales no pueden tener un valor [null](./language-reference/keywords/null.md), pero se pueden crear tipos de valor que aceptan valores NULL mediante la adición de un carácter **?** después del tipo. Por ejemplo, **int?** es un tipo **int** que también puede tener el valor [null](./language-reference/keywords/null.md). En CTS, los tipos que aceptan valores NULL son instancias del tipo struct genérico <xref:System.Nullable%601>. Los tipos que aceptan valores NULL son especialmente útiles cuando se pasan datos hacia y desde bases de datos en las que los valores numéricos podrían ser nulos. Para obtener más información, vea [Tipos que aceptan valores NULL (Guía de programación de C#)](./programming-guide/nullable-types/index.md).

## <a name="see-also"></a>Vea también

- [Clases](classes.md)
- [Tipos básicos](basic-types.md)
