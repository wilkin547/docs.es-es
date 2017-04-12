---
title: "El atributo &quot;Extension&quot; puede aplicarse únicamente a las declaraciones &quot;Module&quot;, &quot;Sub&quot; o &quot;Function&quot; | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3eee008f737bf625023b6e4d58e1df7d282148d3
ms.lasthandoff: 03/13/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>El atributo 'Extension' puede aplicarse únicamente a las declaraciones 'Module', 'Sub' o 'Function'
La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar. El método de extensión puede ser un `Sub` procedimiento o una `Function` procedimiento. Todos los métodos de extensión se deben marcar con el atributo de extensión `<Extension()>`, desde el <xref:System.Runtime.CompilerServices?displayProperty=fullName>espacio de nombres.</xref:System.Runtime.CompilerServices?displayProperty=fullName> Opcionalmente, se puede marcar un módulo que contiene un método de extensión de la misma manera. Ningún otro uso del atributo de extensión es válido.  
  
 **Id. de error:** BC36550  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite el atributo de extensión.  
  
-   Vuelva a diseñar la extensión como un método, definido en un módulo envolvente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `Print` método para el `String` el tipo de datos.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Métodos de extensión](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
