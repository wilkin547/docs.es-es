---
title: "Palabras clave de C# | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cs.keywords"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "@ (palabra clave)"
  - "lenguaje C#, palabras clave"
  - "palabras clave [C#]"
  - "Visual C#, palabras clave"
ms.assetid: e929b0f2-4b92-4d37-8060-23d323b098ad
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Palabras clave de C# #
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Las palabras clave son identificadores predefinidos reservados que tienen un significado especial para el compilador.  No se pueden utilizar como identificadores en un programa a menos que incluyan el carácter `@` como prefijo.  Por ejemplo, `@if` es un identificador válido pero `if` no lo es porque `if` es una palabra clave.  
  
 En la primera tabla de este tema se enumeran las palabras clave que son identificadores reservados en cualquier parte de un programa de C\#.  En la segunda tabla de este tema se enumeran las palabras clave contextuales en C\#.  Las palabras clave contextuales solamente tienen un significado especial en un contexto de programa limitado y se pueden utilizar como identificadores fuera de ese contexto.  Normalmente, al agregarse nuevas palabras clave al lenguaje C\#, éstas se agregan como palabras clave contextuales para evitar errores en programas escritos en versiones anteriores.  
  
|||||  
|-|-|-|-|  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|[as](../../../csharp/language-reference/keywords/as.md)|[base](../../../csharp/language-reference/keywords/base.md)|[bool](../../../csharp/language-reference/keywords/bool.md)|  
|[break](../../../csharp/language-reference/keywords/break.md)|[byte](../../../csharp/language-reference/keywords/byte.md)|[case](../../../csharp/language-reference/keywords/switch.md)|[catch](../../../csharp/language-reference/keywords/try-catch.md)|  
|[char](../../../csharp/language-reference/keywords/char.md)|[checked](../../../csharp/language-reference/keywords/checked.md)|[clase](../../../csharp/language-reference/keywords/class.md)|[const](../../../csharp/language-reference/keywords/const.md)|  
|[continue](../../../csharp/language-reference/keywords/continue.md)|[decimal](../../../csharp/language-reference/keywords/decimal.md)|[default](../../../csharp/language-reference/keywords/default.md)|[delegado](../../../csharp/language-reference/keywords/delegate.md)|  
|[do](../../../csharp/language-reference/keywords/do.md)|[double](../../../csharp/language-reference/keywords/double.md)|[else](../../../csharp/language-reference/keywords/if-else.md)|[enum](../../../csharp/language-reference/keywords/enum.md)|  
|[event](../../../csharp/language-reference/keywords/event.md)|[explicit](../../../csharp/language-reference/keywords/explicit.md)|[extern](../../../csharp/language-reference/keywords/extern.md)|[false](../../../csharp/language-reference/keywords/false.md)|  
|[finally](../../../csharp/language-reference/keywords/try-finally.md)|[fixed](../../../csharp/language-reference/keywords/fixed-statement.md)|[float](../../../csharp/language-reference/keywords/float.md)|[for](../../../csharp/language-reference/keywords/for.md)|  
|[foreach](../../../csharp/language-reference/keywords/foreach-in.md)|[goto](../../../csharp/language-reference/keywords/goto.md)|[if](../../../csharp/language-reference/keywords/if-else.md)|[implicit](../../../csharp/language-reference/keywords/implicit.md)|  
|[in](../../../csharp/language-reference/keywords/foreach-in.md)|[in \(modificador genérico\)](../../../csharp/language-reference/keywords/in-generic-modifier.md)|[Valor int.](../../../csharp/language-reference/keywords/int.md)|[interfaz](../../../csharp/language-reference/keywords/interface.md)|  
|[internal](../../../csharp/language-reference/keywords/internal.md)|[es](../../../csharp/language-reference/keywords/is.md)|[bloquear](../../../csharp/language-reference/keywords/lock-statement.md)|[long](../../../csharp/language-reference/keywords/long.md)|  
|[Espacio de nombres](../../../csharp/language-reference/keywords/namespace.md)|[new](../../../csharp/language-reference/keywords/new.md)|[null](../../../csharp/language-reference/keywords/null.md)|[Objeto.](../../../csharp/language-reference/keywords/object.md)|  
|[':?'.](../../../csharp/language-reference/keywords/operator.md)|[out](../../../csharp/language-reference/keywords/out.md)|[out \(modificador genérico\)](../../../csharp/language-reference/keywords/out-generic-modifier.md)|[override](../../../csharp/language-reference/keywords/override.md)|  
|[params](../../../csharp/language-reference/keywords/params.md)|[private](../../../csharp/language-reference/keywords/private.md)|[protected](../../../csharp/language-reference/keywords/protected.md)|[public](../../../csharp/language-reference/keywords/public.md)|  
|[readonly](../../../csharp/language-reference/keywords/readonly.md)|[ref](../../../csharp/language-reference/keywords/ref.md)|[return](../../../csharp/language-reference/keywords/return.md)|[sbyte](../../../csharp/language-reference/keywords/sbyte.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|[short](../../../csharp/language-reference/keywords/short.md)|[sizeof](../../../csharp/language-reference/keywords/sizeof.md)|[stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)|  
|[static](../../../csharp/language-reference/keywords/static.md)|[string](../../../csharp/language-reference/keywords/string.md)|[struct](../../../csharp/language-reference/keywords/struct.md)|[switch](../../../csharp/language-reference/keywords/switch.md)|  
|[this](../../../csharp/language-reference/keywords/this.md)|[throw](../../../csharp/language-reference/keywords/throw.md)|[true](../../../csharp/language-reference/keywords/true.md)|[try](../../../csharp/language-reference/keywords/try-catch.md)|  
|[typeof](../../../csharp/language-reference/keywords/typeof.md)|[uint](../../../csharp/language-reference/keywords/uint.md)|[ulong](../../../csharp/language-reference/keywords/ulong.md)|[unchecked](../../../csharp/language-reference/keywords/unchecked.md)|  
|[unsafe](../../../csharp/language-reference/keywords/unsafe.md)|[ushort](../../../csharp/language-reference/keywords/ushort.md)|[using](../../../csharp/language-reference/keywords/using.md)|[virtual](../../../csharp/language-reference/keywords/virtual.md)|  
|[void](../../../csharp/language-reference/keywords/void.md)|[volatile](../../../csharp/language-reference/keywords/volatile.md)|[while](../../../csharp/language-reference/keywords/while.md)||  
  
## Palabras clave contextuales  
 Las palabras clave contextuales se utilizan para proporcionar un significado concreto en el código, sin embargo no son palabras reservadas de C\#.  Algunas palabras clave contextuales, como `partial` y `where`, tienen significados especiales en dos o más contextos.  
  
||||  
|-|-|-|  
|[agregar](../../../csharp/language-reference/keywords/add.md)|[alias](../../../csharp/language-reference/keywords/extern-alias.md)|[ascending](../../../csharp/language-reference/keywords/ascending.md)|  
|[async](../../../csharp/language-reference/keywords/async.md)|[espera](../../../csharp/language-reference/keywords/await.md)|[descending](../../../csharp/language-reference/keywords/descending.md)|  
|[dynamic](../../../csharp/language-reference/keywords/dynamic.md)|[from](../../../csharp/language-reference/keywords/from-clause.md)|[obtener](../../../csharp/language-reference/keywords/get.md)|  
|[global](../../../csharp/language-reference/keywords/global.md)|[group](../../../csharp/language-reference/keywords/group-clause.md)|[into](../../../csharp/language-reference/keywords/into.md)|  
|[join](../../../csharp/language-reference/keywords/join-clause.md)|[let](../../../csharp/language-reference/keywords/let-clause.md)|[orderby](../../../csharp/language-reference/keywords/orderby-clause.md)|  
|[partial \(tipo\)](../../../csharp/language-reference/keywords/partial-type.md)|[partial \(método\)](../../../csharp/language-reference/keywords/partial-method.md)|[remove](../../../csharp/language-reference/keywords/remove.md)|  
|[select](../../../csharp/language-reference/keywords/select-clause.md)|[set](../../../csharp/language-reference/keywords/set.md)|[value](../../../csharp/language-reference/keywords/value.md)|  
|[var](../../../csharp/language-reference/keywords/var.md)|[where \(restricción de tipo genérico\)](../../../csharp/language-reference/keywords/where-generic-type-constraint.md)|[where \(cláusula de consulta\)](../../../csharp/language-reference/keywords/where-clause.md)|  
|[yield](../../../csharp/language-reference/keywords/yield.md)||  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)