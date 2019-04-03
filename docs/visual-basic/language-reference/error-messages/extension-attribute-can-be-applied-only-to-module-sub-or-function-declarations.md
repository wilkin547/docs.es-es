---
title: El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826189"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>El atributo 'Extension' sólo se puede aplicar a las declaraciones 'Module', 'Sub' o 'Function'
La única manera de extender un tipo de datos en Visual Basic es definir un método de extensión dentro de un módulo estándar. El método de extensión puede ser un `Sub` procedimiento o un `Function` procedimiento. Todos los métodos de extensión se deben marcar con el atributo de extensión, `<Extension()>`, desde el <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> espacio de nombres. Si lo desea, se puede marcar un módulo que contiene un método de extensión de la misma manera. Ningún otro uso del atributo de extensión es válido.  
  
 **Identificador de error:** BC36550  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite el atributo de extensión.  
  
-   Vuelva a diseñar la extensión como un método, definido en un módulo envolvente.  
  
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

- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Métodos de extensión](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
