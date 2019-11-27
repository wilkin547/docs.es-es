---
title: Mid (Instrucción)
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
ms.openlocfilehash: eeef4c13743b75a3d5e61ac46afb94d9ea105b7a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348025"
---
# <a name="mid-statement"></a>Mid (Instrucción)
Reemplaza un número especificado de caracteres de una variable de `String` por caracteres de otra cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Elementos  
 `Target`  
 Obligatorio. Nombre de la variable de `String` que se va a modificar.  
  
 `Start`  
 Obligatorio. `Integer` expresión. Posición de carácter en `Target` donde comienza la sustitución del texto. `Start` usa un índice basado en uno.  
  
 `Length`  
 Opcional. `Integer` expresión. Número de caracteres que se van a reemplazar. Si se omite, se usa todo `String`.  
  
 `StringExpression`  
 Obligatorio. `String` expresión que reemplaza a parte de `Target`.  
  
## <a name="exceptions"></a>Excepciones  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` < = 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Comentarios  
 El número de caracteres reemplazados siempre es menor o igual que el número de caracteres de `Target`.  
  
 Visual Basic tiene una función <xref:Microsoft.VisualBasic.Strings.Mid%2A> y una instrucción `Mid`. Estos elementos operan en un número especificado de caracteres de una cadena, pero la función `Mid` devuelve los caracteres mientras la instrucción `Mid` reemplaza los caracteres. Para obtener más información, consulta <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> La `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres. Se usa principalmente para convertir cadenas en aplicaciones de juegos de caracteres de doble byte (DBCS). Todas las cadenas de Visual Basic están en Unicode y ya no se admiten `MidB`.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza la instrucción `Mid` para reemplazar un número especificado de caracteres de una variable de cadena por caracteres de otra cadena.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Strings`  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Cadenas](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [Introducción a las cadenas en Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
