---
title: Valores devueltos y variables locales de tipo ref (Guía de C#)
description: Obtenga información sobre cómo definir y usar valores locales y devueltos de tipo ref
author: rpetrusha
ms.author: ronpet
ms.date: 01/23/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: c37c6dd61ae02813bcc467982f3b175da9136e4a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="ref-returns-and-ref-locals"></a>Valores devueltos y variables locales de tipo ref

A partir de C# 7, C# admite los valores devueltos de referencia (valores devueltos de tipo ref). Un valor devuelto de referencia permite que un método devuelva una referencia a una variable, en lugar de un valor, al autor de una llamada. El autor de la llamada puede tratar la variable devuelta como si se hubiera devuelto por valor o por referencia. El autor de la llamada puede crear una variable que sea una referencia al valor devuelto, lo que se conoce como una referencia local.

## <a name="what-is-a-reference-return-value"></a>¿Qué es un valor devuelto de referencia?

La mayoría de los desarrolladores están familiarizados con pasar un argumento a un método llamado *por referencia*. La lista de argumentos de un método llamado incluye una variable pasada por referencia y los cambios que realiza en su valor el método llamado los observa el autor de la llamada. Un *valor devuelto de referencia* significa que un método devuelve una *referencia* o un alias a alguna variable cuyo ámbito incluye el método y cuya duración debe extenderse más allá de la devolución del método. Las modificaciones en el valor del método devuelto por el autor de la llamada se realizan en la variable devuelta por el método.

Declarar que un método devuelve un *valor devuelto de referencia* indica que el método devuelve un alias a una variable. El diseño suele pretender que el código de llamada acceda a dicha variable con el alias, incluso para modificarla. Por tanto, los métodos devueltos por referencia no pueden tener el tipo de valor devuelto `void`.

Hay algunas restricciones en la expresión que un método puede devolver como un valor devuelto de referencia. Se incluyen los siguientes:

- El valor devuelto debe tener una duración que se extienda más allá de la ejecución del método. En otras palabras, no puede tratarse de una variable local del método que la devuelve. Puede ser una instancia o un campo estático de una clase, o puede ser un argumento pasado al método. Al intentar devolver una variable local, se genera el error del compilador CS8168, "No se puede devolver por referencia la variable local 'obj' porque no es de tipo ref".

- El valor devuelto no puede ser el literal `null`. Si intenta devolver `null`, se genera el error del compilador CS8156, "No se puede usar una expresión en este contexto porque no se puede devolver por referencia".

   Un método con un valor devuelto de referencia puede devolver un alias a una variable cuyo valor es actualmente el valor null (sin instancias) o un [tipo que acepta valores NULL](../nullable-types/index.md) para un tipo de valor.
 
- El valor devuelto no puede ser una constante, un miembro de enumeración, el valor devuelto por valor desde una propiedad o un método de `class` o `struct`. Si intenta devolver estos, se genera el error del compilador CS8156, "No se puede usar una expresión en este contexto porque no se puede devolver por referencia".

Además, puesto que un método asincrónico puede volver antes de que haya terminado de ejecutarse, mientras su valor devuelto siga siendo desconocido, los valores devueltos de referencia no se permiten en métodos asincrónicos.
 
## <a name="defining-a-ref-return-value"></a>Definir un valor devuelto de tipo ref

Para definir un valor devuelto de tipo ref, agregue la palabra clave [ref](../../language-reference/keywords/ref.md) al tipo de valor devuelto de la firma del método. Por ejemplo, la siguiente firma indica que la propiedad `GetContactInformation` devuelve una referencia a un objeto `Person` al autor de la llamada:

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

Además, el nombre del objeto devuelto por cada instrucción [return](../../language-reference/keywords/return.md) en el cuerpo del método debe ir precedido de la palabra clave [ref](../../language-reference/keywords/ref.md). Por ejemplo, la siguiente instrucción `return` devuelve una referencia a un objeto `Person` denominado `p`:

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>Usar un valor devuelto de tipo ref

El valor devuelto de tipo ref es un alias para otra variable en el ámbito del método llamado. Puede interpretar cualquier uso del valor devuelto tipo ref como si se usara la variable a la que se asigna el alias:

- Al asignar su valor, se asigna un valor a la variable a la que se asigna el alias.
- Al leer su valor, se lee un valor a la variable a la que se asigna el alias.
- Si la devolución se realiza *por referencia*, entonces devuelve un alias a esa misma variable.
- Si pasa el valor a otro método *por referencia*, pasará una referencia a la variable a la que se asigna el alias.
- Al asignar un alias [local tipo ref](#ref-local), crea un alias para la misma variable.


## <a name="ref-locals"></a>Variables locales de tipo ref

Suponga que el método `GetContactInformation` se declara como un valor devuelto tipo ref:

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

Una asignación por valor lee el valor de una variable y lo asigna a una nueva variable:

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

La asignación anterior declara `p` como una variable local. Su valor inicial se copia a partir de la lectura del valor devuelto por `GetContactInformation`. Las asignaciones futuras a `p` no cambiarán el valor de la variable devuelta por `GetContactInformation`. La variable `p` ya no es un alias de la variable devuelta.

Se declara una variable *local tipo ref* para copiar el alias en el valor original. En la siguiente asignación, `p` es un alias para la variable devuelta desde `GetContactInformation`.

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

El uso posterior de `p` es lo mismo que usar la variable devuelta por `GetContactInformation`, porque `p` es un alias para dicha variable. Los cambios realizados en `p` también modifican la variable devuelta desde `GetContactInformation`.

Tenga en cuenta que la palabra clave `ref` se usa antes de la declaración de variable local *y* antes de la llamada al método. 

Puede acceder a un valor por referencia de la misma manera. En algunos casos, acceder a un valor por referencia aumenta el rendimiento, ya que evita una operación de copia potencialmente cara. Por ejemplo, en la instrucción siguiente se muestra cómo es posible definir un valor local de referencia que se usa para hacer referencia a un valor.

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

Tenga en cuenta que la palabra clave `ref` se usa antes de la declaración de variable local *y* antes del valor en el segundo ejemplo. Si no se incluyen ambas palabras clave `ref` en la asignación y declaración de variable en ambos ejemplos, se produce el error del compilador CS8172, "No se puede inicializar una variable por referencia con un valor". 
 
## <a name="ref-returns-and-ref-locals-an-example"></a>Valores devueltos y variables locales de tipo ref: un ejemplo

En el ejemplo siguiente, se define una clase `NumberStore` que almacena una matriz de valores enteros. El método `FindNumber` devuelve por referencia el primer número que es mayor o igual que el número que se pasa como argumento. Si ningún número es mayor o igual que el argumento, el método devuelve el número en el índice 0. 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

En el ejemplo siguiente, se llama al método `NumberStore.FindNumber` para recuperar el primer valor que es mayor o igual que 16. Después, el autor de la llamada duplica el valor devuelto por el método. Como se muestra en el resultado del ejemplo, este cambio se refleja en el valor de los elementos de matriz de la instancia `NumberStore`.

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

Sin que se admitan los valores devueltos de referencia, este tipo de operación se realiza normalmente devolviendo el índice del elemento de matriz junto con su valor. Después, el autor de la llamada puede usar este índice para modificar el valor en una llamada al método independiente. En cambio, el autor de la llamada también puede modificar el índice para tener acceso a otros valores de matriz y, posiblemente, modificarlos.  
 
## <a name="see-also"></a>Vea también

[ref (palabra clave)](../../language-reference/keywords/ref.md)  
[Semántica de referencia con tipos de valor](../../../csharp/reference-semantics-with-value-types.md)
