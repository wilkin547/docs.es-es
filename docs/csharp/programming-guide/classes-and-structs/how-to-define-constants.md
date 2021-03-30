---
title: Definición de constantes en C#
description: Aprenda a definir constantes de C#, que son campos cuyos valores se establecen en tiempo de compilación. Use constantes para proporcionar nombres descriptivos a los valores especiales.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 54b8a335279c8bb81bc75d182ec653e434ab45a0
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105636862"
---
# <a name="how-to-define-constants-in-c"></a>Definición de constantes en C\#

Las constantes son campos cuyos valores se establecen en tiempo de compilación y nunca se pueden cambiar. Use constantes para proporcionar nombres descriptivos en lugar de literales numéricos ("números mágicos") para valores especiales.  
  
> [!NOTE]
> En C#, la directiva del preprocesador [#define](../../language-reference/preprocessor-directives.md#defining-symbols) no puede usarse para definir constantes en la manera que se usa normalmente en C y C++.  
  
 Para definir valores constantes de tipos enteros (`int`, `byte` y así sucesivamente) use un tipo enumerado. Para más información, vea [enum](../../language-reference/builtin-types/enum.md).  
  
 Para definir constantes no enteras, un enfoque es agruparlas en una única clase estática denominada `Constants`. Esto necesitará que todas las referencias a las constantes vayan precedidas por el nombre de clase, como se muestra en el ejemplo siguiente.  
  
## <a name="example"></a>Ejemplo  

 [!code-csharp[constants](snippets/how-to-define-constants/Program.cs)]  
  
 El uso del calificador de nombre de clase ayuda a garantizar que usted y otros usuarios que usan la constante comprenden que es una constante y que no puede modificarse.  
  
## <a name="see-also"></a>Consulte también

- [Clases y structs](./index.md)
