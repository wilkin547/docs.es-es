---
title: "Mid (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e385d6838daa16d45903c6b270fc47ad88797845
ms.lasthandoff: 03/13/2017

---
# <a name="mid-statement"></a>Mid (Instrucción)
Reemplaza un número especificado de caracteres de un `String` variables con caracteres de otra cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Elementos  
 `Target`  
 Obligatorio. Nombre de la `String` variable va a modificar.  
  
 `Start`  
 Obligatorio. `Integer`expresión. Posición de carácter de `Target` donde comienza el reemplazo de texto. `Start`utiliza un índice basado en uno.  
  
 `Length`  
 Opcional. `Integer`expresión. Número de caracteres que se va a reemplazar. Si omite todos `String` se utiliza.  
  
 `StringExpression`  
 Obligatorio. `String`Expresión que reemplaza parte de `Target`.  
  
## <a name="exceptions"></a>Excepciones  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException></xref:System.ArgumentException>|`Start`<= 0="" or=""></=>`Length`< 0.></ 0.>|  
  
## <a name="remarks"></a>Comentarios  
 El número de caracteres reemplazados siempre es menor o igual que el número de caracteres en `Target`.  
  
 Visual Basic tiene un <xref:Microsoft.VisualBasic.Strings.Mid%2A>(función) y un `Mid` instrucción.</xref:Microsoft.VisualBasic.Strings.Mid%2A> Estos elementos funcionan en un número especificado de caracteres de una cadena, pero la `Mid` función devuelve los caracteres mientras el `Mid` instrucción reemplaza los caracteres. Para obtener más información, consulte <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A>  
  
> [!NOTE]
>  El `MidB` instrucción de versiones anteriores de Visual Basic devuelve una subcadena en bytes, en lugar de caracteres. Se utiliza principalmente para convertir cadenas en aplicaciones de caracteres de doble byte (DBCS). Todas las cadenas de Visual Basic están en Unicode, y `MidB` ya no se admite.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena con caracteres de otra cadena.  
  
 [!code-vb[VbVbalrStrings&#5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:**`Strings`  
  
 **Ensamblado:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 [Cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md)   
 [Introducción a las cadenas en Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
