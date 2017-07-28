---
title: '#<a name="pragma-warning-c-reference"></a>pragma warning (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 75c11acfd096d36c96ceb9e9c5c0d16e47e58fa1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-warning-c-reference"></a>#pragma warning (Referencia de C#)
`#pragma warning` puede habilitar o deshabilitar determinadas advertencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a>Parámetros  
 `warning-list`  
 Una lista separada por comas de números de advertencia. El prefijo "CS" es opcional.  
  
 Cuando no se especifica ningún número de advertencia, `disable` deshabilita todas las advertencias y `restore` habilita todas las advertencias.  
  
> [!NOTE]
>  Para buscar los números de advertencia en Visual Studio, compile el proyecto y después busque los números de advertencia en la ventana **Salida**.  
  
## <a name="example"></a>Ejemplo  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [Errores del compilador de C#](../../../csharp/language-reference/compiler-messages/index.md)

