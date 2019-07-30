---
title: Punto de entrada
description: Obtenga información sobre cómo establecer el punto de entrada F# en un programa que se compila como un archivo ejecutable, donde la ejecución se inicia formalmente.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630519"
---
# <a name="entry-point"></a>Punto de entrada

En este tema se describe el método que se usa para establecer el punto de F# entrada en un programa.

## <a name="syntax"></a>Sintaxis

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Let-function-Binding* es la definición de una función en un `let` enlace.

El punto de entrada a un programa que se compila como un archivo ejecutable es donde se inicia la ejecución formalmente. Para especificar el punto de entrada a F# una aplicación, aplique `EntryPoint` el atributo a la función `main` del programa. Esta función (creada mediante un `let` enlace) debe ser la última función del último archivo compilado. El último archivo compilado es el último archivo del proyecto o el último archivo que se pasa a la línea de comandos.

La función de punto de entrada `string array -> int`tiene el tipo. Los argumentos proporcionados en la línea de comandos se pasan `main` a la función en la matriz de cadenas. El primer elemento de la matriz es el primer argumento; el nombre del archivo ejecutable no se incluye en la matriz, como en otros lenguajes. El valor devuelto se usa como código de salida para el proceso. Cero suele indicar Success; los valores distintos de cero indican un error. No hay ninguna Convención para el significado específico de códigos de retorno distintos de cero; los significados de los códigos de retorno son específicos de la aplicación.

En el ejemplo siguiente se muestra una `main` función simple.

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

Cuando este código se ejecuta con la línea `EntryPoint.exe 1 2 3`de comandos, el resultado es el siguiente.

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a>Punto de entrada implícito

Cuando un programa no tiene ningún atributo **EntryPoint** que indique explícitamente el punto de entrada, los enlaces de nivel superior del último archivo que se va a compilar se usan como punto de entrada.

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
- [Enlaces let](let-bindings.md)
