---
title: "&#39; Extensión &#39; atributo se puede aplicar únicamente a &#39; Módulo &#39; &#39; Sub &#39; o &#39; Función &#39; declaraciones"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords: BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a>&#39; Extensión &#39; atributo se puede aplicar únicamente a &#39; Módulo &#39; &#39; Sub &#39; o &#39; Función &#39; declaraciones
La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar. El método de extensión puede ser un `Sub` procedimiento o una `Function` procedimiento. Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres. Si lo desea, se puede marcar un módulo que contiene un método de extensión de la misma manera. Ningún otro uso del atributo de extensión es válido.  
  
 **Id. de error:** BC36550  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite el atributo de extensión.  
  
-   Vuelva a diseñar la extensión como un método, definido en un módulo contenedor.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define un `Print` método para el `String` tipo de datos.  
  
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
