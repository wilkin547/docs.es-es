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
ms.openlocfilehash: 928917d25b5f3f97c4b8cdff85efdaa1957be41e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626690"
---
# <a name="c-keywords"></a>Palabras clave de C#

Las palabras clave son identificadores reservados predefinidos que tienen un significado especial para el compilador. No podrá utilizarlos como identificadores en el programa a no ser que incluyan `@` como prefijo. Por ejemplo, `@if` es un identificador válido, pero `if` no lo es, porque `if` es una palabra clave.  
  
 En la primera tabla de este tema se muestran las palabras clave que son identificadores reservados en cualquier parte de un programa en C#. En la segunda tabla de este tema se enumeran las palabras clave contextuales en C#. Las palabras clave contextuales tienen un significado especial solo en un contexto de programa limitado y pueden utilizarse como identificadores fuera de ese contexto. Por lo general, cuando se agregan nuevas palabras clave al lenguaje C#, se agregan como palabras clave contextuales para evitar la interrupción de los programas escritos en versiones anteriores.  
  
|||||  
|---|---|---|---|  
|[abstract](abstract.md)|[as](../operators/type-testing-and-cast.md#as-operator)|[base](base.md)|[bool](../builtin-types/bool.md)|  
|[break](break.md)|[byte](../builtin-types/integral-numeric-types.md)|[case](switch.md)|[catch](try-catch.md)|  
|[char](../builtin-types/char.md)|[checked](checked.md)|[class](class.md)|[const](const.md)|  
|[continue](continue.md)|[decimal](../builtin-types/floating-point-numeric-types.md)|[default](default.md)|[delegate](../builtin-types/reference-types.md)|  
|[do](do.md)|[double](../builtin-types/floating-point-numeric-types.md)|[else](if-else.md)|[enum](../builtin-types/enum.md)|  
|[event](event.md)|[explicit](../operators/user-defined-conversion-operators.md)|[extern](extern.md)|[false](../builtin-types/bool.md)|  
|[finally](try-finally.md)|[fixed](fixed-statement.md)|[float](../builtin-types/floating-point-numeric-types.md)|[for](for.md)|  
|[foreach](foreach-in.md)|[goto](goto.md)|[if](if-else.md)|[implicit](../operators/user-defined-conversion-operators.md)|  
|[in](in.md)|[int](../builtin-types/integral-numeric-types.md)|[interface](interface.md)|[internal](internal.md)|
|[is](is.md)|[lock](lock-statement.md)|[long](../builtin-types/integral-numeric-types.md)|[namespace](namespace.md)|
|[new](../operators/new-operator.md)|[null](null.md)|[object](../builtin-types/reference-types.md)|[operator](../operators/operator-overloading.md)|
|[out](out.md)|[override](override.md)|[params](params.md)|[private](private.md)|
|[protected](protected.md)|[public](public.md)|[readonly](readonly.md)|[ref](ref.md)|
|[return](return.md)|[sbyte](../builtin-types/integral-numeric-types.md)|[sealed](sealed.md)|[short](../builtin-types/integral-numeric-types.md)||
[sizeof](../operators/sizeof.md)|[stackalloc](../operators/stackalloc.md)|[static](static.md)|[string](../builtin-types/reference-types.md)|
|[struct](../builtin-types/struct.md)|[switch](switch.md)|[this](this.md)|[throw](throw.md)|
|[true](../builtin-types/bool.md)|[try](try-catch.md)|[typeof](../operators/type-testing-and-cast.md#typeof-operator)|[uint](../builtin-types/integral-numeric-types.md)|
|[ulong](../builtin-types/integral-numeric-types.md)|[unchecked](unchecked.md)|[unsafe](unsafe.md)|[ushort](../builtin-types/integral-numeric-types.md)|
|[using](using.md)|[using static](using-static.md)|[virtual](virtual.md)|[void](../builtin-types/void.md)|
|[volatile](volatile.md)|[while](while.md)|

## <a name="contextual-keywords"></a>Palabras clave contextuales

 Las palabras clave contextuales se usan para proporcionar un significado específico en el código, pero no son una palabra reservada en C#. Algunas palabras clave contextuales, como `partial` y `where`, tienen significados especiales en dos o más contextos.  
  
||||  
|---|---|---|  
|[add](add.md)|[alias](extern-alias.md)|[ascending](ascending.md)|
|[async](async.md)|[await](../operators/await.md)|[by](by.md)|
|[descending](descending.md)|[dynamic](../builtin-types/reference-types.md)|[equals](equals.md)|
|[from](from-clause.md)|[get](get.md)|[global](../operators/namespace-alias-qualifier.md)|
|[group](group-clause.md)|[into](into.md)|[join](join-clause.md)|
|[let](let-clause.md)|[nameof](../operators/nameof.md)|[on](on.md)|
|[orderby](orderby-clause.md)|[partial (tipo)](partial-type.md)|[partial (método)](partial-method.md)|
|[remove](remove.md)|[select](select-clause.md)|[set](set.md)|
|[unmanaged (restricción de tipo genérico)](where-generic-type-constraint.md)|[value](value.md)|[var](var.md)|
|[when (condición de filtro)](when.md)|[where (restricción de tipo genérico)](where-generic-type-constraint.md)|[where (cláusula de consulta)](where-clause.md)|
|[yield](yield.md)| | |
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
