---
title: Punto de entrada (F#)
description: 'Obtenga información sobre cómo establecer el punto de entrada a un programa de F # que se compila como un archivo ejecutable, dónde formalmente comienza la ejecución.'
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698398"
---
# <a name="entry-point"></a>Punto de entrada

Este tema describe el método que se utiliza para establecer el punto de entrada a un programa de F #.

## <a name="syntax"></a>Sintaxis

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *enlace de función permiten* es la definición de una función en un `let` enlace.

El punto de entrada a un programa que se compila como un archivo ejecutable es dónde formalmente comienza la ejecución. Especificar el punto de entrada a una aplicación de F # aplicando el `EntryPoint` atributo para el programa `main` función. Esta función (creada mediante un `let` enlace) debe ser la última función en el último archivo compilado. El último archivo compilado es el último archivo del proyecto o el último archivo que se pasa a la línea de comandos.

La función de punto de entrada tiene el tipo `string array -> int`. Los argumentos proporcionados en la línea de comandos se pasan a la `main` función en la matriz de cadenas. El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes. El valor devuelto se utiliza como el código de salida para el proceso. Cero indica normalmente correctamente; valores distintos de cero indican un error. No hay ninguna convención para el significado específico de los códigos de retorno distinto de cero; los significados de los códigos de retorno son específicos de la aplicación.

El ejemplo siguiente muestra un sencillo `main` función.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Cuando se ejecuta este código con la línea de comandos `EntryPoint.exe 1 2 3`, el resultado es como sigue.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto de entrada implícito

Cuando un programa no tiene ningún **EntryPoint** atributo que indica el punto de entrada, los enlaces de nivel superior en el último archivo para compilarse de forma explícita se utilizan como punto de entrada.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
- [Enlaces let](let-bindings.md)
