---
title: Control de acceso
description: Obtenga información sobre cómo controlar el acceso a elementos de programación como tipos, métodos y funciones, en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 8db178b26f3beb6ce95bff84ccad9ac9e8c40ce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772741"
---
# <a name="access-control"></a>Control de acceso

*Control de acceso* se refiere a declarar qué clientes pueden utilizar ciertos elementos del programa, como tipos, métodos y funciones.

## <a name="basics-of-access-control"></a>Conceptos básicos de Control de acceso

En F#, los especificadores de control de acceso `public`, `internal`, y `private` puede aplicarse a los módulos, tipos, métodos, las definiciones de valor, funciones, propiedades y campos explícitos.

- `public` indica que la entidad puede tener acceso a todos los llamadores.

- `internal` indica que la entidad se puede acceder solo desde el mismo ensamblado.

- `private` indica que la entidad se puede acceder solo desde el tipo o módulo envolvente.

> [!NOTE]
> El especificador de acceso `protected` no se utiliza en F#, aunque es aceptable si se utilizan tipos creados en lenguajes que admiten `protected` acceso. Por lo tanto, si invalida un método protegido, el método sigue siendo accesible únicamente dentro de la clase y sus descendientes.

En general, el especificador se coloca delante del nombre de la entidad, excepto cuando una `mutable` o `inline` especificador se usa, que aparecen después del especificador de control de acceso.

Si no se utiliza ningún especificador de acceso, el valor predeterminado es `public`, excepto para `let` enlaces en un tipo, que siempre son `private` al tipo.

Las firmas en F# proporcionan otro mecanismo para controlar el acceso a F# elementos del programa. Las firmas no son necesarias para el control de acceso. Para más información, vea [Signatures](signatures.md) (Firmas).

## <a name="rules-for-access-control"></a>Reglas de Control de acceso

Control de acceso está sujeto a las reglas siguientes:

- Las declaraciones de herencia (es decir, el uso de `inherit` para especificar una clase base para una clase), las declaraciones (es decir, especificar que una clase implementa una interfaz) de la interfaz y abstraer los miembros siempre tienen la misma accesibilidad que el tipo envolvente. Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.

- Accesibilidad para los casos individuales de una unión discriminada viene determinada por la accesibilidad de la propia unión discriminada. Es decir, un caso de unión concreto no menos accesible que la propia unión.

- Accesibilidad para campos individuales de un tipo de registro no viene determinada por la accesibilidad del mismo registro. Es decir, una etiqueta de registro concreto no menos accesible que el mismo registro.

## <a name="example"></a>Ejemplo

El código siguiente muestra el uso de especificadores de control de acceso. Hay dos archivos en el proyecto, `Module1.fs` y `Module2.fs`. Cada archivo es implícitamente un módulo. Por lo tanto, hay dos módulos, `Module1` y `Module2`. Un tipo privado y un tipo interno se definen en `Module1`. El tipo privado no es accesible desde `Module2`, pero puede tipo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

El código siguiente comprueba la accesibilidad de los tipos creados en `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Firmas](signatures.md)