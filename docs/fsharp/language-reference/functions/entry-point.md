---
title: Punto de entrada (F#)
description: 'Obtenga información acerca de cómo establecer el punto de entrada a un programa de F # que se compila como un archivo ejecutable, dónde formalmente comienza la ejecución.'
ms.date: 05/16/2016
ms.openlocfilehash: 3d6cab755dd89f2d3d669a8763aa08660432a0ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563625"
---
# <a name="entry-point"></a>Punto de entrada

Este tema describe el método que use para establecer el punto de entrada a un programa en F #.


## <a name="syntax"></a>Sintaxis

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Comentarios
En la sintaxis anterior, *enlace de función permiten* es la definición de una función en un `let` enlace.

El punto de entrada a un programa que se compila como un archivo ejecutable es dónde formalmente comienza la ejecución. Especifique el punto de entrada a una aplicación de F # aplicando la `EntryPoint` de atributo para el programa `main` función. Esta función (creada mediante una `let` enlace) debe ser la última función del último archivo compilado. El último archivo compilado es el último archivo de proyecto o el último archivo que se pasa a la línea de comandos.

La función de punto de entrada tiene el tipo `string array -> int`. Los argumentos proporcionados en la línea de comandos se pasan a la `main` función en la matriz de cadenas. El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes. El valor devuelto se utiliza como el código de salida para el proceso. Cero normalmente indica éxito; valores distintos de cero indican un error. No hay ninguna convención para el significado específico de los códigos de retorno es distinto de cero; los significados de los códigos de retorno son específicos de la aplicación.

En el ejemplo siguiente se muestra un sencillo `main` función.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

Cuando se ejecuta este código con la línea de comandos `EntryPoint.exe 1 2 3`, el resultado es como sigue.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto de entrada implícito
Cuando un programa no tiene ningún **EntryPoint** atributo que indica el punto de entrada, los enlaces de nivel superior en el último archivo para compilarse de forma explícita se utilizan como el punto de entrada.


## <a name="see-also"></a>Vea también
[Funciones](index.md)

[Enlaces let](let-bindings.md)
