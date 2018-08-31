---
title: '#warning (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932682"
---
# <a name="warning-c-reference"></a>#warning (Referencia de C#)
`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código. Por ejemplo:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Comentarios
 Un uso común de `#warning` es en una directiva condicional. También es posible generar un error definido por el usuario con [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).  
  
## <a name="example"></a>Ejemplo  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)
