---
title: Funciones de cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: f6c7f28cee03c2d5ac258cf1e2c8956225334f7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="string-functions-visual-basic"></a>Funciones de cadena (Visual Basic)
En la tabla siguiente se enumera las funciones que proporciona Visual Basic para buscar y manipular cadenas.  
  
|Método de .NET framework|Descripción|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Devuelve un `Integer` valor que representa el código de carácter correspondiente a un carácter.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Devuelve el carácter asociado al código de carácter especificado.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Devuelve una matriz de base cero que contiene un subconjunto de un `String` matriz basándose en criterios de filtro especificados.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Devuelve una cadena con formato según las instrucciones contenidas en un formato `String` expresión.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Devuelve una expresión con formato como un valor de moneda mediante el símbolo de moneda definido en el panel de control del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Devuelve una expresión de cadena que representa un valor de fecha y hora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Devuelve una expresión con formato de un número.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Devuelve una expresión con formato de porcentaje (es decir, multiplicada por 100) con un carácter % final.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Devuelve un entero que especifica la posición inicial de la primera aparición de una cadena dentro de otra.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Devuelve la posición de la primera aparición de una cadena dentro de otra, empezando por el lado derecho de la cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Devuelve una cadena creada mediante la combinación de un número de subcadenas contenidas en una matriz.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Devuelve una cadena o carácter convertido a minúsculas.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Devuelve una cadena que contiene un número especificado de caracteres del lado izquierdo de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Devuelve un entero que contiene el número de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Devuelve una cadena alineada a la izquierda que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Devuelve una cadena que contiene un número especificado de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Devuelve una cadena en la que una subcadena especificada se ha reemplazado por otra subcadena un número especificado de veces.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Devuelve una cadena que contiene un número especificado de caracteres desde el lado derecho de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Devuelve una cadena alineada a la derecha que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios finales.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Devuelve una cadena que consta del número especificado de espacios.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Devuelve una matriz unidimensional de base cero que contiene un número especificado de subcadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Devuelve -1, 0 o 1, en función del resultado de una comparación de cadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Devuelve una cadena convertida según lo especificado.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Devuelve una cadena u objeto que se compone del carácter especificado repetido el número especificado de veces.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Devuelve una cadena en la que se invierte el orden de los caracteres de una cadena especificada.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales ni finales.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Devuelve una cadena o un carácter que contiene la cadena especificada convertida en mayúsculas.|  
  
 Puede usar el [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) determinado por la configuración regional del sistema de criterio de ordenación de instrucción que se debe establecer si se comparan las cadenas con un texto entre mayúsculas y minúsculas (`Text`) o por las representaciones binarias internas de los caracteres ( `Binary`). El método de comparación de texto predeterminado es `Binary`.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `UCase` función para devolver una versión en mayúsculas de una cadena.  
  
 [!code-vb[VbVbalrStrings#31](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `LTrim` función para quitar los espacios iniciales y la `RTrim` espacios de función para quitar los finales de una variable de cadena. Usa el `Trim` función para quitar ambos tipos de espacios.  
  
 [!code-vb[VbVbalrStrings#25](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `Mid` función devuelva un número especificado de caracteres de una cadena.  
  
 [!code-vb[VbVbalrStrings#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza `Len` para devolver el número de caracteres en una cadena.  
  
 [!code-vb[VbVbalrStrings#33](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_4.vb)]  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `InStr` función para devolver la posición de la primera aparición de una cadena dentro de otra.  
  
 [!code-vb[VbVbalrStrings#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_5.vb)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra varios usos de la `Format` función para dar formato a valores utilizando tanto `String` formatos y formatos definidos por el usuario. Para el separador de fecha (`/`), separador de hora (`:`) y los indicadores de AM/PM (`t` y `tt`), el resultado con formato real mostrado por el sistema depende de la configuración regional que se está usando el código. Cuando horas y fechas se muestran en el entorno de desarrollo, se utilizan el formato de hora corta y el formato de fecha corta de la configuración regional del código.  
  
> [!NOTE]
>  Para las configuraciones regionales que utilizan el reloj de 24 horas, los indicadores de AM/PM (`t` y `tt`) mostrar nada.  
  
 [!code-vb[VbVbalrStrings#27](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_6.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)  
 [Resumen de manipulación de cadenas](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
