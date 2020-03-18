---
title: 'Utilizar propiedades: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: d873f626b660bb6bd94710add4543e21e11823d6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77452024"
---
# <a name="using-properties-c-programming-guide"></a>Utilizar propiedades (Guía de programación de C#)

Las propiedades combinan aspectos de los campos y los métodos. Para el usuario de un objeto, una propiedad que parece un campo, el acceso a la propiedad necesita la misma sintaxis. Para el implementador de una clase, una propiedad es uno o dos bloques de código que representa un descriptor de acceso [get](../../language-reference/keywords/get.md) o un descriptor de acceso [set](../../language-reference/keywords/set.md). El bloque de código del descriptor de acceso `get` se ejecuta cuando se lee la propiedad; el bloque de código del descriptor de acceso `set` se ejecuta cuando se asigna un nuevo valor a la propiedad. Una propiedad sin un descriptor de acceso `set` se considera de solo lectura. Una propiedad sin un descriptor de acceso `get` se considera de solo escritura. Una propiedad que tiene ambos descriptores de acceso es de lectura y escritura.

A diferencia de los campos, las propiedades no se clasifican como variables. Por lo tanto, no puede pasar una propiedad como un parámetro [ref](../../language-reference/keywords/ref.md) u [out](../../language-reference/keywords/out-parameter-modifier.md).

Las propiedades tienen muchos usos: pueden validar datos antes de permitir un cambio; pueden exponer claramente datos en una clase donde esos datos se recuperan realmente de otros orígenes, como una base de datos; pueden realizar una acción cuando los datos se cambian, como generar un evento, o cambiar el valor de otros campos.

Las propiedades se declaran en el bloque de clase especificando el nivel de acceso del campo, seguido del tipo de la propiedad, seguido del nombre de la propiedad y seguido de un bloque de código que declara un descriptor de acceso `get` o un descriptor de acceso `set`. Por ejemplo:

[!code-csharp[csProgGuideProperties#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#7)]

En este ejemplo, `Month` se declara como una propiedad, de manera que el descriptor de acceso `set` pueda estar seguro de que el valor `Month` se establece entre 1 y 12. La propiedad `Month` usa un campo privado para realizar un seguimiento del valor actual. A menudo, a la ubicación real de los datos de una propiedad se le conoce como la "memoria auxiliar" de la propiedad. Esto es común para las propiedades que usan campos privados como una memoria auxiliar. El campo se marca como privado para asegurarse de que solo puede cambiarse llamando a la propiedad. Para obtener más información sobre las restricciones de acceso público y privado, vea [Modificadores de acceso](./access-modifiers.md).

Las propiedades implementadas automáticamente proporcionan una sintaxis simplificada para las declaraciones de propiedad simples. Para obtener más información, vea [Auto-Implemented Properties](auto-implemented-properties.md) (Propiedades implementadas automáticamente).

## <a name="the-get-accessor"></a>El descriptor de acceso get

El cuerpo del descriptor de acceso `get` se parece al de un método. Debe devolver un valor del tipo de propiedad. La ejecución del descriptor de acceso `get` es equivalente a la lectura del valor del campo. Por ejemplo, cuando se devuelve la variable privada del descriptor de acceso `get` y se habilitan las optimizaciones, la llamada al método de descriptor de acceso `get` se inserta mediante el compilador, de manera que no existe ninguna sobrecarga de llamada al método. En cambio, un método de descriptor de acceso `get` virtual no puede insertarse porque el compilador no conoce en tiempo de compilación a qué método puede llamarse realmente en tiempo de ejecución. A continuación se muestra un descriptor de acceso `get` que devuelve el valor de un campo privado `_name`:

[!code-csharp[csProgGuideProperties#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#8)]

Cuando hace referencia a la propiedad, excepto como el destino de una asignación, el descriptor de acceso `get` se invoca para leer el valor de la propiedad. Por ejemplo:

[!code-csharp[csProgGuideProperties#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#9)]

El descriptor de acceso `get` debe finalizar en una instrucción [return](../../language-reference/keywords/return.md) o [throw](../../language-reference/keywords/throw.md), y el control no puede salir del cuerpo del descriptor de acceso.

Cambiar el estado del objeto mediante el descriptor de acceso `get` es un estilo de programación incorrecto. Por ejemplo, el siguiente descriptor de acceso produce el efecto secundario de cambiar el estado del objeto cada vez que se tiene acceso al campo `_number`.

[!code-csharp[csProgGuideProperties#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#10)]

El descriptor de acceso `get` puede usarse para devolver el valor de campo o para calcularlo y devolverlo. Por ejemplo:

[!code-csharp[csProgGuideProperties#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#11)]

En el segmento de código anterior, si no asigna un valor a la propiedad `Name`, devolverá el valor `NA`.

## <a name="the-set-accessor"></a>El descriptor de acceso set

El descriptor de acceso `set` es similar a un método cuyo tipo de valor devuelto es [void](../../language-reference/builtin-types/void.md). Usa un parámetro implícito denominado `value`, cuyo tipo es el tipo de la propiedad. En el siguiente ejemplo, se agrega un descriptor de acceso `set` a la propiedad `Name`:

[!code-csharp[csProgGuideProperties#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#12)]

Cuando asigna un valor a la propiedad, el descriptor de acceso `set` se invoca mediante un argumento que proporciona el valor nuevo. Por ejemplo:

[!code-csharp[csProgGuideProperties#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#13)]

Es un error usar el nombre de parámetro implícito, `value`, para una declaración de variable local en el descriptor de acceso `set`.

## <a name="remarks"></a>Comentarios

Las propiedades pueden marcarse como `public`, `private`, `protected`, `internal`, `protected internal` o `private protected`. Estos modificadores de acceso definen cómo los usuarios de la clase pueden obtener acceso a la propiedad. Los descriptores de acceso `get` y `set` para la misma propiedad pueden tener diferentes modificadores de acceso. Por ejemplo, `get` puede ser `public` para permitir el acceso de solo lectura desde el exterior del tipo, y `set` puede ser `private` o `protected`. Para obtener más información, vea [Modificadores de acceso](./access-modifiers.md).

Una propiedad puede declararse como una propiedad estática mediante la palabra clave `static`. Esto hace que la propiedad esté disponible para los autores de la llamada en cualquier momento, aunque no exista ninguna instancia de la clase. Para obtener más información, consulte [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).

Una propiedad puede marcarse como una propiedad virtual mediante la palabra clave [virtual](../../language-reference/keywords/virtual.md). Esto permite que las clases derivadas invaliden el comportamiento de la propiedad mediante la palabra clave [override](../../language-reference/keywords/override.md). Para obtener más información sobre estas opciones, vea [Herencia](inheritance.md).

Una propiedad que invalida una propiedad virtual también puede [sellarse](../../language-reference/keywords/sealed.md), que especifica que para las clases derivadas ya no es virtual. Por último, una propiedad puede declararse [abstracta](../../language-reference/keywords/abstract.md). Esto significa que no existe ninguna implementación en la clase, y las clases derivadas deben escribir su propia implementación. Para obtener más información sobre estas opciones, vea [Clases y miembros de clase abstractos y sellados (Guía de programación de C#)](abstract-and-sealed-classes-and-class-members.md).
  
> [!NOTE]
> Es un error usar un modificador [virtual](../../language-reference/keywords/virtual.md), [abstract](../../language-reference/keywords/abstract.md) u [override](../../language-reference/keywords/override.md) en un descriptor de acceso de una propiedad [static](../../language-reference/keywords/static.md).

## <a name="example"></a>Ejemplo

En este ejemplo se muestran las propiedades de solo lectura, estáticas y de instancia. Acepta el nombre del empleado desde el teclado, incrementa `NumberOfEmployees` en 1 y muestra el nombre del empleado y el número.

[!code-csharp[csProgGuideProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#2)]

## <a name="example"></a>Ejemplo

En este ejemplo se muestra cómo tener acceso a una propiedad en una clase base que está oculta mediante otra propiedad que tiene el mismo nombre en una clase derivada:

[!code-csharp[csProgGuideProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#3)]

A continuación se muestran puntos importantes del ejemplo anterior:

- La propiedad `Name` de la clase derivada oculta la propiedad `Name` de la clase base. En dicho caso, el modificador `new` se usa en la declaración de la propiedad en la clase derivada:

     [!code-csharp[csProgGuideProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#4)]  

- La conversión `(Employee)` se usa para tener acceso a la propiedad oculta de la clase base:

     [!code-csharp[csProgGuideProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#5)]

     Para obtener más información sobre cómo ocultar miembros, vea el [Modificador new](../../language-reference/keywords/new-modifier.md).

## <a name="example"></a>Ejemplo

En este ejemplo, dos clases, `Cube` y `Square`, implementan una clase abstracta, `Shape`, e invalidan su propiedad `Area` abstracta. Tenga en cuenta el uso del modificador [override](../../language-reference/keywords/override.md) en las propiedades. El programa acepta el lado como una entrada y calcula las áreas del cuadrado y el cubo. También acepta el área como una entrada y calcula el lado correspondiente para el cuadrado y el cubo.

[!code-csharp[csProgGuideProperties#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#6)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Propiedades](properties.md)
- [Propiedades de interfaz](interface-properties.md)
- [Propiedades autoimplementadas](auto-implemented-properties.md)
