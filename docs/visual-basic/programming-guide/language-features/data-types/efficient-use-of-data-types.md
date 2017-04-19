---
title: Uso eficiente de tipos de datos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function, preferred to Asc
- data types [Visual Basic], using efficiently
- optimization, data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function, preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
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
ms.openlocfilehash: b81a1c81d970beee32925c3f2fe6ca3bcad79151
ms.lasthandoff: 03/13/2017

---
# <a name="efficient-use-of-data-types-visual-basic"></a>Uso eficiente de tipos de datos (Visual Basic)
Las variables no declaradas y las variables declaradas sin un tipo de datos se les asigna el `Object` tipo de datos. Resulta muy fácil escribir programas rápidamente, pero puede provocar que se ejecuten más lentamente.  
  
## <a name="strong-typing"></a>Seguro escribiendo  
 Especificar los tipos de datos para todas las variables se conoce como *establecimiento inflexible de tipos*. Uso de establecimiento inflexible de tipos tiene varias ventajas:  
  
-   Habilita la compatibilidad con IntelliSense para las variables. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.  
  
-   Aprovecha las ventajas de la comprobación de tipo compilador. Detectar las instrucciones que pueden fallar en tiempo de ejecución debido a errores como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.  
  
-   Da como resultado una ejecución más rápida del código.  
  
## <a name="most-efficient-data-types"></a>Tipos de datos más eficaces  
 Para las variables que contienen nunca valores decimales, los tipos de datos enteros son más eficaces que los tipos no integrales. En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], `Integer` y `UInteger` son los tipos numéricos más eficaces.  
  
 Para los números fraccionarios, `Double` es el tipo de datos más eficaz, porque los procesadores de plataformas actuales realizan operaciones de punto flotante de precisión doble. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
## <a name="specifying-data-type"></a>Especifica el tipo de datos  
 Utilice la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico. Simultáneamente, puede especificar su nivel de acceso mediante el [público](../../../../visual-basic/language-reference/modifiers/public.md), [protegido](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, como en el ejemplo siguiente.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Conversión de caracteres  
 El `AscW` y `ChrW` funciones funcionan en Unicode. Se deben utilizar en lugar de a `Asc` y `Chr`, que deben traducir a y desde Unicode.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A></xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A></xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A></xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)   
 [Declaración de variable](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Usar IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense)
