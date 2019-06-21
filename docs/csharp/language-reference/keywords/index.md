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
ms.openlocfilehash: 1aff57186f08a651aaf5e8dfaa988b5fb296768d
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306601"
---
# <a name="c-keywords"></a>Palabras clave de C#

Las palabras clave son identificadores reservados predefinidos que tienen un significado especial para el compilador. No podrá utilizarlos como identificadores en el programa a no ser que incluyan `@` como prefijo. Por ejemplo, `@if` es un identificador válido, pero `if` no lo es, porque `if` es una palabra clave.  
  
 En la primera tabla de este tema se muestran las palabras clave que son identificadores reservados en cualquier parte de un programa en C#. En la segunda tabla de este tema se enumeran las palabras clave contextuales en C#. Las palabras clave contextuales tienen un significado especial solo en un contexto de programa limitado y pueden utilizarse como identificadores fuera de ese contexto. Por lo general, cuando se agregan nuevas palabras clave al lenguaje C#, se agregan como palabras clave contextuales para evitar la interrupción de los programas escritos en versiones anteriores.  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](../operators/type-testing-and-conversion-operators.md#as-operator)|[base](base.md)|[bool](bool.md)|  
|[break](break.md)|[byte](byte.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](decimal.md)|[default](default.md)|[delegate](delegate.md)|  
|[do](do.md)|[double](double.md)|[else](if-else.md)|[enum](enum.md)|  
|[event](event.md)|[explicit](explicit.md)|[extern](extern.md)|[false](false-literal.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](float.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](implicit.md)|  
|[in](in.md)|[int](int.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](long.md)|[namespace](namespace.md)|
|[new](new.md)|[null](null.md)|[object](object.md)|[operator](operator.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](sbyte.md)|[sealed](sealed.md)|[short](short.md)||
[sizeof](sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](string.md)|
|[struct](struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](true-literal.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator)|[uint](uint.md)|
|[ulong](ulong.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](ushort.md)|
|[using](using.md)|[using static](using-static.md)|[virtual](virtual.md)|[void](void.md)|
|[volatile](volatile.md)|[while](while.md)|

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

- [Referencia de C#](../index.md)
