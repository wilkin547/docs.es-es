---
title: Control de acceso
description: Obtenga información sobre cómo controlar el acceso a elementos de programación, como tipos, métodos y funciones, en F# el lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: ed77a09cf87aabf9a4134276e89e84aa42abd3c3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629958"
---
# <a name="access-control"></a>Control de acceso

El *control de acceso* hace referencia a la declaración de los clientes que pueden usar determinados elementos de programa, como tipos, métodos y funciones.

## <a name="basics-of-access-control"></a>Aspectos básicos de Access Control

En F#, los especificadores `public`de control de `internal`acceso, `private` y se pueden aplicar a módulos, tipos, métodos, definiciones de valores, funciones, propiedades y campos explícitos.

- `public`indica que todos los llamadores pueden tener acceso a la entidad.

- `internal`indica que solo se puede tener acceso a la entidad desde el mismo ensamblado.

- `private`indica que solo se puede tener acceso a la entidad desde el tipo o módulo envolvente.

> [!NOTE]
> El especificador `protected` de acceso no se utiliza F#en, aunque es aceptable si se usan tipos creados en lenguajes que admiten `protected` el acceso. Por consiguiente, si invalida un método protegido, el método permanece accesible solo dentro de la clase y sus descendientes.

En general, el especificador se coloca delante del nombre de la entidad, excepto cuando se usa un `mutable` especificador o `inline` , que aparecen después del especificador de control de acceso.

Si no se usa ningún especificador de acceso, el `public`valor predeterminado es `let` , excepto para los enlaces de un tipo, `private` que siempre son del tipo.

Las firmas de F# proporcionan otro mecanismo para controlar el acceso F# a los elementos del programa. No se necesitan firmas para el control de acceso. Para más información, vea [Signatures](signatures.md) (Firmas).

## <a name="rules-for-access-control"></a>Reglas para Access Control

El control de acceso está sujeto a las siguientes reglas:

- Las declaraciones de herencia (es decir, el uso `inherit` de para especificar una clase base para una clase), las declaraciones de interfaz (es decir, la especificación de que una clase implementa una interfaz) y los miembros abstractos siempre tienen la misma accesibilidad que el tipo envolvente. Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.

- La accesibilidad de los casos individuales en una Unión discriminada viene determinada por la accesibilidad de la propia Unión discriminada. Es decir, un caso de Unión determinado no es menos accesible que la propia Unión.

- La accesibilidad del propio registro no puede determinar la accesibilidad de los campos individuales de un tipo de registro. Es decir, una etiqueta de registro determinada no es menos accesible que el propio registro.

## <a name="example"></a>Ejemplo

En el código siguiente se muestra el uso de especificadores de control de acceso. Hay dos archivos en el proyecto, `Module1.fs` y. `Module2.fs` Cada archivo es implícitamente un módulo. Por lo tanto, hay dos módulos `Module1` , `Module2`y. En `Module1`se definen un tipo privado y un tipo interno. No se puede tener acceso al tipo privado `Module2`desde, pero el tipo interno puede.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

En el código siguiente se prueba la accesibilidad de los tipos `Module1.fs`creados en.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Firmas](signatures.md)
