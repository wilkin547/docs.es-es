---
title: Palabras clave de C#
ms.date: 03/07/2017
f1_keywords:
- cs.keywords
helpviewer_keywords:
- keywords [C#]
- C# language, keywords
- Visual C#, keywords
- '@ keyword'
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
ms.openlocfilehash: 7ad8f037b2a4d8b0d4e386f2c7380047c6c29332
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300389"
---
# <a name="c-keywords"></a>Palabras clave de C#

Las palabras clave son identificadores reservados predefinidos que tienen un significado especial para el compilador. No podrá utilizarlos como identificadores en el programa a no ser que incluyan `@` como prefijo. Por ejemplo, `@if` es un identificador válido, pero `if` no lo es, porque `if` es una palabra clave.  
  
 En la primera tabla de este tema se muestran las palabras clave que son identificadores reservados en cualquier parte de un programa en C#. En la segunda tabla de este tema se enumeran las palabras clave contextuales en C#. Las palabras clave contextuales tienen un significado especial solo en un contexto de programa limitado y pueden utilizarse como identificadores fuera de ese contexto. Por lo general, cuando se agregan nuevas palabras clave al lenguaje C#, se agregan como palabras clave contextuales para evitar la interrupción de los programas escritos en versiones anteriores.  
  
|||||  
|---|---|---|---|  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|[as](../../../csharp/language-reference/keywords/as.md)|[base](../../../csharp/language-reference/keywords/base.md)|[bool](../../../csharp/language-reference/keywords/bool.md)|  
|[break](../../../csharp/language-reference/keywords/break.md)|[byte](../../../csharp/language-reference/keywords/byte.md)|[case](../../../csharp/language-reference/keywords/switch.md)|[catch](../../../csharp/language-reference/keywords/try-catch.md)|  
|[char](../../../csharp/language-reference/keywords/char.md)|[checked](../../../csharp/language-reference/keywords/checked.md)|[class](../../../csharp/language-reference/keywords/class.md)|[const](../../../csharp/language-reference/keywords/const.md)|  
|[continue](../../../csharp/language-reference/keywords/continue.md)|[decimal](../../../csharp/language-reference/keywords/decimal.md)|[default](../../../csharp/language-reference/keywords/default.md)|[delegate](../../../csharp/language-reference/keywords/delegate.md)|  
|[do](../../../csharp/language-reference/keywords/do.md)|[double](../../../csharp/language-reference/keywords/double.md)|[else](../../../csharp/language-reference/keywords/if-else.md)|[enum](../../../csharp/language-reference/keywords/enum.md)|  
|[event](../../../csharp/language-reference/keywords/event.md)|[explicit](../../../csharp/language-reference/keywords/explicit.md)|[extern](../../../csharp/language-reference/keywords/extern.md)|[false](false-literal.md)|  
|[finally](../../../csharp/language-reference/keywords/try-finally.md)|[fixed](../../../csharp/language-reference/keywords/fixed-statement.md)|[float](../../../csharp/language-reference/keywords/float.md)|[for](../../../csharp/language-reference/keywords/for.md)|  
|[foreach](../../../csharp/language-reference/keywords/foreach-in.md)|[goto](../../../csharp/language-reference/keywords/goto.md)|[if](../../../csharp/language-reference/keywords/if-else.md)|[implicit](../../../csharp/language-reference/keywords/implicit.md)|  
|[in](../../../csharp/language-reference/keywords/in.md)|[int](../../../csharp/language-reference/keywords/int.md)|[interface](../../../csharp/language-reference/keywords/interface.md)|[internal](../../../csharp/language-reference/keywords/internal.md)|
|[is](../../../csharp/language-reference/keywords/is.md)|[lock](../../../csharp/language-reference/keywords/lock-statement.md)|[long](../../../csharp/language-reference/keywords/long.md)|[namespace](../../../csharp/language-reference/keywords/namespace.md)|
|[new](../../../csharp/language-reference/keywords/new.md)|[null](../../../csharp/language-reference/keywords/null.md)|[object](../../../csharp/language-reference/keywords/object.md)|[operator](../../../csharp/language-reference/keywords/operator.md)|
|[out](../../../csharp/language-reference/keywords/out.md)|[override](../../../csharp/language-reference/keywords/override.md)|[params](../../../csharp/language-reference/keywords/params.md)|[private](../../../csharp/language-reference/keywords/private.md)|
|[protected](../../../csharp/language-reference/keywords/protected.md)|[public](../../../csharp/language-reference/keywords/public.md)|[readonly](../../../csharp/language-reference/keywords/readonly.md)|[ref](../../../csharp/language-reference/keywords/ref.md)|
|[return](../../../csharp/language-reference/keywords/return.md)|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|[sealed](../../../csharp/language-reference/keywords/sealed.md)|[short](../../../csharp/language-reference/keywords/short.md)||
[sizeof](../../../csharp/language-reference/keywords/sizeof.md)|[stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)|[static](../../../csharp/language-reference/keywords/static.md)|[string](../../../csharp/language-reference/keywords/string.md)|
|[struct](../../../csharp/language-reference/keywords/struct.md)|[switch](../../../csharp/language-reference/keywords/switch.md)|[this](../../../csharp/language-reference/keywords/this.md)|[throw](../../../csharp/language-reference/keywords/throw.md)|
|[true](true-literal.md)|[try](../../../csharp/language-reference/keywords/try-catch.md)|[typeof](../../../csharp/language-reference/keywords/typeof.md)|[uint](../../../csharp/language-reference/keywords/uint.md)|
|[ulong](../../../csharp/language-reference/keywords/ulong.md)|[unchecked](../../../csharp/language-reference/keywords/unchecked.md)|[unsafe](../../../csharp/language-reference/keywords/unsafe.md)|[ushort](../../../csharp/language-reference/keywords/ushort.md)|
|[using](../../../csharp/language-reference/keywords/using.md)|[using static](using-static.md)|[virtual](../../../csharp/language-reference/keywords/virtual.md)|[void](../../../csharp/language-reference/keywords/void.md)|
|[volatile](../../../csharp/language-reference/keywords/volatile.md)|[while](../../../csharp/language-reference/keywords/while.md)|

## <a name="contextual-keywords"></a>Palabras clave contextuales

 Las palabras clave contextuales se usan para proporcionar un significado específico en el código, pero no son una palabra reservada en C#. Algunas palabras clave contextuales, como `partial` y `where`, tienen significados especiales en dos o más contextos.  
  
||||  
|---|---|---|  
|[add](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](await.md)|[by](by.md)|
|[descending](descending.md)|[dynamic](dynamic.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[global](global.md)|
|[group](group-clause.md)|[into](into.md)|[join](join-clause.md)|
|[let](let-clause.md)|[nameof](nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (tipo)](partial-type.md)|[partial (método)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[value](value.md)|[var](var.md)|[when (condición de filtro)](when.md)|
|[where (restricción de tipo genérico)](where-generic-type-constraint.md)|[where (cláusula de consulta)](where-clause.md)|[yield](yield.md)|
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
