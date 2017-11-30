---
title: Control de acceso (F#)
description: "Obtener información sobre cómo controlar el acceso a elementos de programación como tipos, métodos y funciones, en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a>Control de acceso

*Control de acceso* se refiere a declarar qué clientes pueden utilizar ciertos elementos del programa, como tipos, métodos y funciones.


## <a name="basics-of-access-control"></a>Conceptos básicos de Control de acceso
En F #, el acceso de control especificadores `public`, `internal`, y `private` pueden aplicarse a los módulos, tipos, métodos, definiciones de valor, funciones, propiedades y campos explícitos.


- `public`indica que la entidad puede tener acceso a todos los llamadores.

- `internal`indica que se puede tener acceso a la entidad únicamente desde el mismo ensamblado.

- `private`indica que la entidad puede tener acceso sólo desde el tipo o módulo envolvente.


>[!NOTE] 
El especificador de acceso `protected` no se utiliza en F #, aunque es aceptable si se utilizan tipos creados en lenguajes que admitan `protected` acceso. Por lo tanto, si invalida un método protegido, el método permanecerá accesible únicamente dentro de la clase y sus descendientes.

En general, el especificador se coloca delante del nombre de la entidad, excepto cuando una `mutable` o `inline` especificador se usa, que aparecen después del especificador de control de acceso.

Si no se utiliza ningún especificador de acceso, el valor predeterminado es `public`, excepto para `let` enlaces en un tipo, que siempre son `private` al tipo.

Las firmas en F # proporcionan otro mecanismo para controlar el acceso a elementos de programa de F #. Las firmas no son necesarias para el control de acceso. Para más información, vea [Signatures](signatures.md) (Firmas).


## <a name="rules-for-access-control"></a>Reglas para el Control de acceso
Control de acceso está sujeto a las reglas siguientes:


- Las declaraciones de herencia (es decir, el uso de `inherit` para especificar una clase base para una clase), interfaz declaraciones (es decir, especificar que una clase implementa una interfaz) y resumir los miembros siempre tienen la misma accesibilidad que el tipo envolvente. Por lo tanto, no se puede usar un especificador de control de acceso en estas construcciones.

- Los casos individuales de una unión discriminada no pueden tener sus propios modificadores de control de acceso independientes del tipo de unión.

- Los campos individuales de un tipo de registro no pueden tener sus propios modificadores de control de acceso independientes del tipo de registro.


## <a name="example"></a>Ejemplo
El código siguiente muestra el uso de especificadores de control de acceso. Hay dos archivos en el proyecto, `Module1.fs` y `Module2.fs`. Cada archivo de forma implícita es un módulo. Por lo tanto, hay dos módulos, `Module1` y `Module2`. Un tipo privado y un tipo interno se definen en `Module1`. No se puede tener acceso a un tipo privado de `Module2`, pero puede del tipo interno.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
El código siguiente comprueba la accesibilidad de los tipos creados en `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Firmas](signatures.md)
