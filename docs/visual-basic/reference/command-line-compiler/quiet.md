---
description: Más información sobre -quiet
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 23e1b6472e80ac6ca2ecea5c4390b43722ccebb6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432733"
---
# <a name="-quiet"></a>-quiet

Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.

## <a name="syntax"></a>Sintaxis

```console
-quiet
```

## <a name="remarks"></a>Comentarios

De forma predeterminada, `-quiet` no está en vigor. Cuando el compilador informa de un error o una advertencia relacionados con la sintaxis, también genera la línea del código fuente. En el caso de las aplicaciones que analizan la salida del compilador, es posible que sea más conveniente que el compilador solo genere el texto del diagnóstico.

En el ejemplo siguiente, `Module1` genera un error que incluye el código fuente cuando se compila sin `-quiet`.

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

Resultado:

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

Compilado con `-quiet`, el compilador solo genera lo siguiente:

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> La opción `-quiet` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.

## <a name="example"></a>Ejemplo

En el código siguiente se compila `T2.vb` y no se muestra el código para el diagnóstico del compilador relacionado con la sintaxis:

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
