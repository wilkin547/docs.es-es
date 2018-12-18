---
title: '#region: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: c306511ad8133d0063ccf8b70f2d34d25d2ad3fa
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244289"
---
# <a name="region-c-reference"></a>#region (Referencia de C#)
`#region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de [esquematización](/visualstudio/ide/outlining) del editor de código de Visual Studio. En archivos de código más largos, es conveniente poder contraer u ocultar una o varias regiones para poder centrarse en la parte del archivo en la que se está trabajando actualmente. En el ejemplo siguiente se muestra cómo definir una región:  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a>Comentarios  
 Un bloque `#region` se debe terminar con una directiva [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).  
  
 Un bloque `#region` no se puede superponer con un bloque [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md). Pero, un bloque `#region` se puede anidar en un bloque `#if` y un bloque `#if` se puede anidar en un bloque `#region`.  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
