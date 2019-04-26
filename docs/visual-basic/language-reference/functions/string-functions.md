---
title: Funciones de cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 645d19219481d22ade90f44aaecb62471eb915d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802006"
---
# <a name="string-functions-visual-basic"></a>Funciones de cadena (Visual Basic)
En la tabla siguiente se enumera las funciones de Visual Basic proporciona para buscar y manipular cadenas.  
  
|Método de .NET framework|Descripción|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Devuelve un `Integer` valor que representa el código de carácter correspondiente a un carácter.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Devuelve el carácter asociado con el código de carácter especificado.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Devuelve una matriz de base cero que contiene un subconjunto de un `String` matriz basándose en criterios de filtro especificados.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Devuelve una cadena con formato según las instrucciones contenidas en un formato `String` expresión.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Devuelve una expresión con formato como un valor de moneda mediante el símbolo de moneda definido en el panel de control del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Devuelve una expresión de cadena que representa un valor de fecha y hora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Devuelve una expresión con formato de número.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Devuelve una expresión con formato de porcentaje (es decir, multiplicada por 100) con un carácter % final.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Devuelve un entero que especifica la posición inicial de la primera aparición de una cadena dentro de otra.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Devuelve la posición de la primera aparición de una cadena dentro de otra, comenzando por el lado derecho de la cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Devuelve una cadena creada mediante la combinación de varias subcadenas contenidas en una matriz.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Devuelve una cadena o un carácter convertidos en minúscula.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Devuelve una cadena que contiene un número especificado de caracteres del lado izquierdo de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Devuelve un entero que contiene el número de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Devuelve una cadena alineada a la izquierda que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Devuelve una cadena que contiene un número especificado de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Devuelve una cadena en el que una subcadena especificada se ha reemplazado por otra subcadena un número especificado de veces.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Devuelve una cadena que contiene un número especificado de caracteres desde el lado derecho de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Devuelve una cadena alineada a la derecha que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios finales.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Devuelve una cadena que consta del número especificado de espacios.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Devuelve una matriz unidimensional de base cero que contiene un número especificado de subcadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Devuelve -1, 0 o 1, en función del resultado de una comparación de cadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Devuelve una cadena convertida según lo especificado.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Devuelve una cadena u objeto que se compone del carácter especificado repetido el número de veces especificado.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Devuelve una cadena en la que se invierte el orden de los caracteres de una cadena especificada.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales o finales.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Devuelve una cadena o un carácter que contiene la cadena especificada convertida en mayúsculas.|  
  
 Puede usar el [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) determinado por la configuración regional del sistema de criterio de ordenación de instrucción para establecer si se comparan las cadenas con un texto de mayúsculas y minúsculas (`Text`) o por las representaciones binarias internas de los caracteres () `Binary`). El método de comparación de texto predeterminado es `Binary`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `UCase` función para devolver una versión de una cadena en mayúsculas.  
  
 [!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `LTrim` función para quitar los espacios iniciales y la `RTrim` espacios de función para quitar los finales de una variable de cadena. Usa el `Trim` función para quitar ambos tipos de espacios.  
  
 [!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `Mid` función devuelva un número especificado de caracteres de una cadena.  
  
 [!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza `Len` para devolver el número de caracteres en una cadena.  
  
 [!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `InStr` función para devolver la posición de la primera aparición de una cadena dentro de otra.  
  
 [!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra varios usos de la `Format` función a los valores de formato mediante ambos `String` formatos y formatos definidos por el usuario. Para el separador de fecha (`/`), separador de hora (`:`) y los indicadores de A.M./P.M. (`t` y `tt`), el formato de salida que muestre su sistema depende de la configuración regional que use el código. Cuando horas y fechas se muestran en el entorno de desarrollo, se usan el formato de hora corta y el formato de fecha corta de la configuración regional del código.  
  
> [!NOTE]
>  Para las configuraciones regionales que utilizan un reloj de 24 horas, los indicadores de A.M./P.M. (`t` y `tt`) no muestran nada.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vea también

- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Resumen de manipulación de cadenas](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
