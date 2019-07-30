---
title: do (Enlaces)
description: Obtenga información sobre F# cómo se usa un enlace ' do ' para ejecutar código sin definir una función o un valor.
ms.date: 05/16/2016
ms.openlocfilehash: f98f523296bfaceeda35d4861eafbfeaa5a60c32
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630532"
---
# <a name="do-bindings"></a>do (Enlaces)

Un `do` enlace se utiliza para ejecutar código sin definir una función o un valor. Además, los enlaces do se pueden usar en las clases, vea [ `do` enlaces en clases](../members/do-bindings-in-classes.md).

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
[ do ]expression
```

## <a name="remarks"></a>Comentarios

Use un `do` enlace cuando desee ejecutar código independientemente de una definición de función o valor. La expresión de un `do` enlace debe devolver `unit`. El código de un enlace de `do` nivel superior se ejecuta cuando se inicializa el módulo. La palabra `do` clave es opcional.

Los atributos se pueden aplicar a un enlace de `do` nivel superior. Por ejemplo, si el programa utiliza la interoperabilidad com, es posible que `STAThread` desee aplicar el atributo a su programa. Para ello, puede usar un atributo en un `do` enlace, tal y como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet201.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](../index.md)
- [Funciones](index.md)
