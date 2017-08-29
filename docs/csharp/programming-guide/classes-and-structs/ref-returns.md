---
title: "Valores devueltos y variables locales de tipo ref (Guía de C#)"
description: "Obtenga información sobre cómo definir y usar valores locales y devueltos de tipo ref"
author: rpetrusha
ms.author: ronpet
ms.date: 05/30/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 18cf7a4b-29f0-4b14-85b8-80af754aabd8
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 753c620e1352dfc5fc57c380c66479c8e2d9b0ee
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ref-returns-and-ref-locals"></a>Valores devueltos y variables locales de tipo ref

A partir de C# 7, C# admite los valores devueltos de referencia (valores devueltos de tipo ref). Un valor devuelto de referencia permite que un método devuelva una referencia a un objeto, en lugar de un valor, al autor de una llamada. El autor de la llamada puede tratar el objeto devuelto como si se hubiera devuelto por valor o por referencia. Un valor devuelto por referencia que el autor de la llamada trata como una referencia en lugar de un valor es una variable local de tipo ref.

## <a name="what-is-a-reference-return-value"></a>¿Qué es un valor devuelto de referencia?

La mayoría de los desarrolladores están familiarizados con pasar un argumento a un método llamado *por referencia*. La lista de argumentos de un método llamado incluye un valor pasado por referencia y los cambios que realiza en su valor el método llamado se devuelven al autor de la llamada. Un *valor devuelto de referencia* es lo contrario:

- El valor devuelto del método llamado, en lugar de un argumento que se le pasa, es una referencia.

- El autor de la llamada, en lugar del método llamado, puede modificar el valor devuelto por el método.

- En lugar de modificaciones al argumento que se reflejan en el estado del objeto en el autor de la llamada, las modificaciones al valor devuelto del método realizadas por el autor de la llamada se reflejan en el estado del objeto cuyo método se ha llamado.

Los valores devueltos de referencia pueden generar código más compacto, así como permitir que un objeto exponga solo los elementos de datos individuales, como un elemento de matriz, que son de interés para el autor de la llamada. Esto reduce la probabilidad de que el autor de la llamada modifique accidentalmente el estado del objeto.

Hay algunas restricciones en el valor que un método puede devolver como un valor devuelto de referencia. Se incluyen los siguientes:

- El valor devuelto no puede ser `void`. Al intentar definir un método con un valor devuelto de referencia `void`, se genera el error del compilador CS1547, "La palabra clave 'void' no se puede usar en este contexto".
 
- El valor devuelto no puede ser una variable local en el método que lo devuelve; debe tener un ámbito que esté fuera del método que lo devuelve. Puede ser una instancia o un campo estático de una clase, o puede ser un argumento pasado al método. Al intentar devolver una variable local, se genera el error del compilador CS8168, "No se puede devolver por referencia la variable local 'obj' porque no es de tipo ref".

- El valor devuelto no puede ser `null`. Si intenta devolver `null`, se genera el error del compilador CS8156, "No se puede usar una expresión en este contexto porque no se puede devolver por referencia".

   Si un método con un valor devuelto de tipo ref necesita devolver un valor NULL, puede devolver un valor NULL (sin instancia) para un tipo de referencia o un [tipo que acepta valores NULL](../nullable-types/index.md) para un tipo de valor.
 
- El valor devuelto no puede ser una constante, un miembro de enumeración o una propiedad de una `class` o `struct`. Si intenta devolver estos, se genera el error del compilador CS8156, "No se puede usar una expresión en este contexto porque no se puede devolver por referencia".

Además, puesto que un método asincrónico puede volver antes de que haya terminado de ejecutarse y se conozca su valor devuelto, los valores devueltos de referencia no se permiten en métodos `async`.
 
## <a name="defining-a-ref-return-value"></a>Definir un valor devuelto de tipo ref

Para definir un valor devuelto de tipo ref, agregue la palabra clave [ref](../../language-reference/keywords/ref.md) al tipo de valor devuelto de la firma del método. Por ejemplo, la siguiente firma indica que la propiedad `GetContactInformation` devuelve una referencia a un objeto `Person` al autor de la llamada:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Además, el nombre del objeto devuelto por cada instrucción [return](../../language-reference/keywords/return.md) en el cuerpo del método debe ir precedido de la palabra clave [ref](../../language-reference/keywords/ref.md). Por ejemplo, la siguiente instrucción `return` devuelve un objeto `Person` denominado `p` por referencia:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Usar un valor devuelto de tipo ref

El autor de una llamada puede controlar un valor devuelto de tipo ref de una de estas dos formas:

- Como un valor normal devuelto por valor desde un método. El autor de la llamada puede optar por omitir que el valor devuelto es un valor devuelto de referencia. En este caso, los cambios realizados en el valor devuelto por la llamada al método no se reflejan en el estado del tipo llamado. Si el valor devuelto es un tipo de valor, los cambios realizados en el valor devuelto por la llamada al método no se reflejan en el estado del tipo llamado.

- Como un valor devuelto de referencia. El autor de la llamada debe definir la variable a la que se asigna el valor devuelto de referencia como una [variable local de tipo ref](#ref-local), y cualquier cambio en el valor devuelto por la llamada al método se refleja en el estado del tipo llamado. 

## <a name="ref-locals"></a>Variables locales de tipo ref

Para controlar el valor devuelto de referencia como una referencia, el autor de la llamada debe declarar el valor para que sea una *variable local de tipo ref* mediante la palabra clave `ref`. Por ejemplo, si el valor devuelto por el método `Person.GetContactInfomation` debe usarse como una referencia en lugar de un valor, la llamada al método aparece como:

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

Tenga en cuenta que la palabra clave `ref` se usa antes de la declaración de variable local *y* antes de la llamada al método. Si no se incluyen ambas palabras clave `ref` en la asignación y declaración de variable, se produce el error del compilador CS8172, "No se puede inicializar una variable por referencia con un valor". 
 
Los cambios posteriores en el objeto `Person` devuelto por el método se reflejan en el objeto `contacts`.

Si `p` no está definido como una variable local de tipo ref mediante la palabra clave `ref`, los cambios que realiza en `p` el autor de la llamada no se reflejan en el objeto `contacts`.
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Valores devueltos y variables locales de tipo ref: un ejemplo

En el ejemplo siguiente, se define una clase `NumberStore` que almacena una matriz de valores enteros. El método `FindNumber` devuelve por referencia el primer número que es mayor o igual que el número que se pasa como argumento. Si ningún número es mayor o igual que el argumento, el método devuelve el número en el índice 0. 

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

En el ejemplo siguiente, se llama al método `NumberStore.FindNumber` para recuperar el primer valor que es mayor o igual que 16. Después, el autor de la llamada duplica el valor devuelto por el método. Como se muestra en el resultado del ejemplo, este cambio se refleja en el valor de los elementos de matriz de la instancia `NumberStore`.

[!CODE-cs[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Sin que se admitan los valores devueltos de referencia, este tipo de operación se realiza normalmente devolviendo el índice del elemento de matriz junto con su valor. Después, el autor de la llamada puede usar este índice para modificar el valor en una llamada al método independiente. En cambio, el autor de la llamada también puede modificar el índice para tener acceso a otros valores de matriz y, posiblemente, modificarlos.  
 
## <a name="see-also"></a>Vea también

[ref (palabra clave)](../../language-reference/keywords/ref.md)

