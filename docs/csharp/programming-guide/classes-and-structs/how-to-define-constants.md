---
title: "Cómo: Definir constantes en C#"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6c5a6f63675893eb0700afab462bf237f5639d74
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-constants-in-c"></a>Cómo: Definir constantes en C#
Las constantes son campos cuyos valores se establecen en tiempo de compilación y nunca se pueden cambiar. Use constantes para proporcionar nombres descriptivos en lugar de literales numéricos ("números mágicos") para valores especiales.  
  
> [!NOTE]
>  En C#, la directiva del preprocesador [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) no puede usarse para definir constantes en la manera que se usa normalmente en C y C++.  
  
 Para definir valores constantes de tipos enteros (`int`, `byte` y así sucesivamente) use un tipo enumerado. Para más información, vea [enum](../../../csharp/language-reference/keywords/enum.md).  
  
 Para definir constantes no enteras, un enfoque es agruparlas en una única clase estática denominada `Constants`. Esto necesitará que todas las referencias a las constantes vayan precedidas por el nombre de clase, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csProgGuideObjects#89](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-constants_1.cs)]  
  
 El uso del calificador de nombre de clase ayuda a garantizar que usted y otros usuarios que usan la constante comprenden que es una constante y que no puede modificarse.  
  
## <a name="see-also"></a>Vea también  
 [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)

