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
ms.openlocfilehash: 0379a6cabe819365b22994a5e4f9353d98b2c768
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873201"
---
# <a name="mid-statement"></a>Mid (Instrucción)

Reemplaza un número especificado de caracteres de una `String` variable por caracteres de otra cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a>Partes  

 `Target`  
 Obligatorio. Nombre de la `String` variable que se va a modificar.  
  
 `Start`  
 Obligatorio. Expresión `Integer`. Posición de carácter en `Target` donde comienza la sustitución del texto. `Start` utiliza un índice basado en uno.  
  
 `Length`  
 Opcional. Expresión `Integer`. Número de caracteres que se van a reemplazar. Si se omite, `String` se usa ALL.  
  
 `StringExpression`  
 Obligatorio. `String` expresión que reemplaza a parte de `Target` .  
  
## <a name="exceptions"></a>Excepciones  
  
|Tipo de excepción|Condición|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|`Start` <= 0 o `Length` < 0.|  
  
## <a name="remarks"></a>Comentarios  

 El número de caracteres reemplazados siempre es menor o igual que el número de caracteres de `Target` .  
  
 Visual Basic tiene una <xref:Microsoft.VisualBasic.Strings.Mid%2A> función y una `Mid` instrucción. Estos elementos operan en un número especificado de caracteres de una cadena, pero la `Mid` función devuelve los caracteres mientras la `Mid` instrucción reemplaza los caracteres. Para obtener más información, vea <xref:Microsoft.VisualBasic.Strings.Mid%2A>.  
  
> [!NOTE]
> La `MidB` instrucción de versiones anteriores de Visual Basic reemplaza una subcadena en bytes, en lugar de caracteres. Se usa principalmente para convertir cadenas en aplicaciones de juegos de caracteres de doble byte (DBCS). Todas las cadenas de Visual Basic están en Unicode y ya `MidB` no se admiten.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se utiliza la `Mid` instrucción para reemplazar un número especificado de caracteres de una variable de cadena por caracteres de otra cadena.  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a>Requisitos  

 **Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Módulo:**`Strings`  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [Cadenas](../../programming-guide/language-features/strings/index.md)
- [Introducción a las cadenas en Visual Basic](../../programming-guide/language-features/strings/introduction-to-strings.md)
