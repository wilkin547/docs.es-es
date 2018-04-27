---
title: Uso eficiente de tipos de datos (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4cac585cdc3072d595d2446e1937678f9ab03335
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="efficient-use-of-data-types-visual-basic"></a>Uso eficiente de tipos de datos (Visual Basic)
Las variables no declaradas y las variables declaradas sin un tipo de datos se les asigna el `Object` tipo de datos. Esto resulta muy sencillo escribir programas rápidamente, pero puede hacer que se ejecute más lentamente.  
  
## <a name="strong-typing"></a>Establecimiento inflexible tipos  
 Especificar los tipos de datos para todas las variables se conoce como *establecimiento inflexible de tipos*. Uso de establecimiento inflexible de tipos tiene varias ventajas:  
  
-   Habilita la compatibilidad con IntelliSense para las variables. Esto le permite ver sus propiedades y otros miembros a medida que escribe en el código.  
  
-   Aprovecha las ventajas de la comprobación de tipos de compilador. Esto detecta las instrucciones que pueden producir un error en tiempo de ejecución debido a errores, como el desbordamiento. También detecta llamadas a métodos en objetos que no las admiten.  
  
-   Se produce una ejecución más rápida del código.  
  
## <a name="most-efficient-data-types"></a>Tipos de datos más eficaces  
 Para las variables que contienen nunca valores decimales, los tipos de datos enteros son más eficaces que los tipos enteros. En Visual Basic, `Integer` y `UInteger` son los tipos numéricos más eficaces.  
  
 Para los números fraccionarios, `Double` es el tipo de datos más eficaz, porque los procesadores en las plataformas actuales realizan operaciones de punto flotante de precisión doble. Sin embargo, las operaciones con `Double` no son tan rápidas como con los tipos enteros como `Integer`.  
  
## <a name="specifying-data-type"></a>Especificar el tipo de datos  
 Use la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar una variable de un tipo específico. Al mismo tiempo, puede especificar su nivel de acceso mediante el [público](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, como en el ejemplo siguiente.  
  
```  
Private x As Double  
Protected s As String  
```  
  
## <a name="character-conversion"></a>Conversión de caracteres  
 El `AscW` y `ChrW` funcionan en Unicode. Se deben utilizar en lugar de a `Asc` y `Chr`, que debe traducir dentro y fuera de Unicode.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de datos numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)  
 [Declaración de variables](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Usar IntelliSense](/visualstudio/ide/using-intellisense)
