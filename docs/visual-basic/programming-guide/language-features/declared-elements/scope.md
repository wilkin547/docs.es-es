---
description: 'Más información acerca de: ámbito en Visual Basic'
title: Ámbito
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 5b5412f5743162bb91fc3651d08f5c7ff9ba8abd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480211"
---
# <a name="scope-in-visual-basic"></a>Ámbito en Visual Basic

El *ámbito* de un elemento declarado es el conjunto de todo el código que puede hacer referencia a él sin calificar su nombre o ponerlo a disposición a través de una [instrucción Imports (espacio de nombres de .net y tipo)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md). Un elemento puede tener el ámbito en uno de los siguientes niveles:

|Nivel|Descripción|
|-----------|-----------------|
|Ámbito de bloque|Solo está disponible en el bloque de código en el que se declara|
|Ámbito del procedimiento|Disponible para todo el código del procedimiento en el que se declara|
|Ámbito del módulo|Disponible para todo el código del módulo, la clase o la estructura en la que se declara|
|Ámbito de espacio de nombres|Disponible para todo el código del espacio de nombres en el que se declara|

Estos niveles de progreso del ámbito van desde el más estrecho (bloque) hasta el más ancho (espacio de nombres), donde el *ámbito más estrecho* significa el conjunto más pequeño de código que puede hacer referencia al elemento sin calificación. Para obtener más información, vea "niveles de ámbito" en esta página.

## <a name="specifying-scope-and-defining-variables"></a>Especificar el ámbito y definir variables

El ámbito de un elemento se especifica cuando se declara. El ámbito puede depender de los siguientes factores:

- Región (bloque, procedimiento, módulo, clase o estructura) en la que se declara el elemento.

- Espacio de nombres que contiene la declaración del elemento.

- Nivel de acceso que se declara para el elemento.

Tenga cuidado al definir variables con el mismo nombre pero con un ámbito diferente, ya que esto puede provocar resultados inesperados. Para obtener más información, consulta [References to Declared Elements](references-to-declared-elements.md).

## <a name="levels-of-scope"></a>Niveles de ámbito

Un elemento de programación está disponible en toda la región en la que se declara. Todo el código de la misma región puede hacer referencia al elemento sin calificar su nombre.

### <a name="block-scope"></a>Ámbito de bloque

Un bloque es un conjunto de instrucciones incluidas en las instrucciones de declaración de inicio y finalización, como las siguientes:

- `Do` y `Loop`

- `For` [ `Each` ] y `Next`

- `If` y `End If`

- `Select` y `End Select`

- `SyncLock` y `End SyncLock`

- `Try` y `End Try`

- `While` y `End While`

- `With` y `End With`

Si declara una variable dentro de un bloque, solo podrá usarla dentro de ese bloque. En el ejemplo siguiente, el ámbito de la variable de entero `cube` es el bloque entre `If` y `End If` , y ya no se puede hacer referencia a `cube` cuando la ejecución pasa fuera del bloque.

```vb
If n < 1291 Then
    Dim cube As Integer
    cube = n ^ 3
End If
```

> [!NOTE]
> Incluso si el ámbito de una variable está limitado a un bloque, su duración sigue siendo la del procedimiento completo. Si especifica el bloque más de una vez durante el procedimiento, cada variable de bloque conserva su valor anterior. Para evitar resultados inesperados en este caso, es aconsejable inicializar las variables de bloque al principio del bloque.

### <a name="procedure-scope"></a>Ámbito del procedimiento

Un elemento declarado dentro de un procedimiento no está disponible fuera de ese procedimiento. Solo el procedimiento que contiene la declaración puede utilizarlo. Las variables de este nivel también se conocen como *variables locales*. Se declaran con la [instrucción Dim](../../../language-reference/statements/dim-statement.md), con o sin la palabra clave [static](../../../language-reference/modifiers/static.md) .

El procedimiento y el ámbito de bloque están estrechamente relacionados. Si declara una variable dentro de un procedimiento pero fuera de un bloque dentro de ese procedimiento, puede considerar que la variable tiene ámbito de bloque, donde el bloque es el procedimiento completo.

> [!NOTE]
> Todos los elementos locales, incluso si son `Static` variables, son privados para el procedimiento en el que aparecen. No se puede declarar ningún elemento mediante la palabra clave [Public](../../../language-reference/modifiers/public.md) dentro de un procedimiento.

### <a name="module-scope"></a>Ámbito del módulo

Para mayor comodidad, el *nivel de módulo* de un solo término se aplica igualmente a los módulos, las clases y las estructuras. Puede declarar elementos en este nivel colocando la instrucción de declaración fuera de cualquier procedimiento o bloque, pero dentro del módulo, clase o estructura.

Al crear una declaración en el nivel de módulo, el nivel de acceso que elija determina el ámbito. El espacio de nombres que contiene el módulo, la clase o la estructura también afecta al ámbito.

Los elementos para los que declara el nivel de acceso [privado](../../../language-reference/modifiers/private.md) están disponibles para todos los procedimientos de ese módulo, pero no para cualquier código de otro módulo. La `Dim` instrucción en el nivel de módulo tiene como valor predeterminado `Private` si no se usa ninguna palabra clave de nivel de acceso. Sin embargo, puede hacer que el ámbito y el nivel de acceso sean más obvios mediante el uso de la `Private` palabra clave en la `Dim` instrucción.

En el ejemplo siguiente, todos los procedimientos definidos en el módulo pueden hacer referencia a la variable de cadena `strMsg` . Cuando se llama al segundo procedimiento, se muestra el contenido de la variable de cadena `strMsg` en un cuadro de diálogo.

```vb
' Put the following declaration at module level (not in any procedure).
Private strMsg As String
' Put the following Sub procedure in the same module.
Sub initializePrivateVariable()
    strMsg = "This variable cannot be used outside this module."
End Sub
' Put the following Sub procedure in the same module.
Sub usePrivateVariable()
    MsgBox(strMsg)
End Sub
```

### <a name="namespace-scope"></a>Ámbito de espacio de nombres

Si declara un elemento en el nivel de módulo mediante la palabra clave [Friend](../../../language-reference/modifiers/friend.md) o [Public](../../../language-reference/modifiers/public.md) , estará disponible para todos los procedimientos en todo el espacio de nombres en el que se declara el elemento. Con la siguiente modificación en el ejemplo anterior, el código puede hacer referencia a la variable de cadena `strMsg` en cualquier lugar del espacio de nombres de su declaración.

```vb
' Include this declaration at module level (not inside any procedure).
Public strMsg As String
```

El ámbito de espacio de nombres incluye espacios de nombres anidados. Un elemento disponible desde dentro de un espacio de nombres también está disponible en cualquier espacio de nombres anidado dentro de ese espacio de nombres.

Si el proyecto no contiene ninguna [instrucción de espacio de nombres](../../../language-reference/statements/namespace-statement.md), todo el proyecto se encuentra en el mismo espacio de nombres. En este caso, el ámbito del espacio de nombres se puede considerar como ámbito del proyecto. `Public` los elementos de un módulo, clase o estructura también están disponibles para cualquier proyecto que haga referencia a su proyecto.

## <a name="choice-of-scope"></a>Elección del ámbito

Al declarar una variable, debe tener en cuenta los siguientes puntos al elegir su ámbito.

### <a name="advantages-of-local-variables"></a>Ventajas de las variables locales

Las variables locales son una buena opción para cualquier tipo de cálculo temporal, por las razones siguientes:

- **Prevención de conflictos de nombres.** Los nombres de las variables locales no son susceptibles de conflictos. Por ejemplo, puede crear varios procedimientos diferentes que contengan una variable denominada `intTemp` . Siempre y cuando cada uno `intTemp` de ellos se declare como una variable local, cada procedimiento solo reconoce su propia versión de `intTemp` . Cualquier procedimiento puede modificar el valor en su local `intTemp` sin afectar a `intTemp` las variables de otros procedimientos.

- **Consumo de memoria.** Las variables locales consumen memoria solo mientras su procedimiento se está ejecutando. La memoria se libera cuando el procedimiento vuelve al código de llamada. Por el contrario, las variables [compartidas](../../../language-reference/modifiers/shared.md) y [estáticas](../../../language-reference/modifiers/static.md) consumen recursos de memoria hasta que la aplicación deja de ejecutarse, por lo que debe usarlas solo cuando sea necesario. *Las variables de instancia* consumen memoria mientras su instancia sigue existiendo, lo que hace que sean menos eficientes que las variables locales, pero que pueden ser más eficaces que `Shared` o `Static` variables.

### <a name="minimizing-scope"></a>Minimizar el ámbito

En general, al declarar cualquier variable o constante, es una buena práctica de programación conseguir que el ámbito sea lo más estrecho posible (el ámbito de bloque es el más estrecho). Esto ayuda a conservar la memoria y minimiza las posibilidades de que el código hace referencia erróneamente a la variable equivocada. Del mismo modo, debe declarar una variable para que sea [estática](../../../language-reference/modifiers/static.md) solo cuando sea necesario conservar su valor entre las llamadas a procedimiento.

## <a name="see-also"></a>Consulte también

- [Características de los elementos declarados](declared-element-characteristics.md)
- [Procedimiento para controlar el ámbito de una variable](how-to-control-the-scope-of-a-variable.md)
- [Período de duración en Visual Basic](lifetime.md)
- [Niveles de acceso en Visual Basic](access-levels.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Declaración de variable](../variables/variable-declaration.md)
