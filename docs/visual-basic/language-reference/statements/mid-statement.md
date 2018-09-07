---
title: Mid (instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44061655"
---
# <a name="mid-statement"></a>Mid (Instrucción)
Reemplaza un número especificado de caracteres de un `String` variable por los caracteres de otra cadena.  
  
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
 Requerido. Nombre de la `String` variable va a modificar.  
  
 `Start`  
 Requerido. `Integer` expresión. Posición de carácter de `Target` donde comienza la sustitución de texto. `Start` utiliza un índice basado en uno.  
  
 `Length`  
 Opcional. `Integer` expresión. Número de caracteres que se va a reemplazar. Si omite todos `String` se utiliza.  
  
 `StringExpression`  
 Requerido. `String` Expresión que reemplaza parte de `Target`.  
  
## <a name="exceptions"></a>Excepciones  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Comentarios  
 El número de caracteres reemplazados siempre es menor o igual que el número de caracteres en `Target`.  
  
 Visual Basic tiene un <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y un `Mid` instrucción. Estos elementos funcionan en un número especificado de caracteres en una cadena, pero la `Mid` función devuelve los caracteres mientras el `Mid` instrucción reemplaza los caracteres. Para obtener más información, consulta <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
>  El `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres. Se utiliza principalmente para convertir cadenas en aplicaciones de caracteres de doble byte (DBCS). Todas las cadenas en Visual Basic están en Unicode, y `MidB` ya no se admite.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena de caracteres de otra cadena.  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Strings`  
  
 **Ensamblado:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [Cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [Introducción a las cadenas en Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
