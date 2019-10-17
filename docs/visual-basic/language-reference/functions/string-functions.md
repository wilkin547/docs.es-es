---
title: Funciones de cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 32a31a881573cc9dc481fc07fc4067569a96a963
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72395827"
---
# <a name="string-functions-visual-basic"></a>Funciones de cadena (Visual Basic)

En la tabla siguiente se enumeran las funciones que Visual Basic proporciona en la clase <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> para buscar y manipular cadenas. Se pueden considerar como Visual Basic funciones intrínsecas; es decir, no tiene que llamarlos como miembros explícitos de una clase, como se muestra en los ejemplos. Los métodos adicionales y, en algunos casos, métodos complementarios, están disponibles en la clase <xref:System.String?displayProperty=nameWithType>. 
  
|Método .NET Framework|Descripción|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Devuelve un valor `Integer` que representa el código de carácter correspondiente a un carácter.|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Devuelve el carácter asociado al código de carácter especificado.|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Devuelve una matriz de base cero que contiene un subconjunto de una matriz `String` basándose en los criterios de filtro especificados.|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Devuelve una cadena con formato según las instrucciones contenidas en un formato @no__t expresión-0.|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Devuelve una expresión con formato de valor de moneda mediante el símbolo de moneda definido en el panel de control del sistema.|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Devuelve una expresión de cadena que representa un valor de fecha y hora.|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Devuelve una expresión con formato de número.|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Devuelve una expresión con formato de porcentaje (es decir, multiplicada por 100) con un carácter % final.|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Devuelve un entero que especifica la posición inicial de la primera aparición de una cadena dentro de otra.|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Devuelve la posición de la primera aparición de una cadena dentro de otra, empezando por el lado derecho de la cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Devuelve una cadena creada mediante la combinación de un número de subcadenas contenidas en una matriz.|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Devuelve una cadena o un carácter convertido a minúsculas.|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Devuelve una cadena que contiene un número especificado de caracteres desde el lado izquierdo de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Devuelve un entero que contiene el número de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Devuelve una cadena alineada a la izquierda que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales.|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Devuelve una cadena que contiene un número especificado de caracteres de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Devuelve una cadena en la que se ha reemplazado una subcadena especificada por otra subcadena un número especificado de veces.|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Devuelve una cadena que contiene un número especificado de caracteres del lado derecho de una cadena.|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Devuelve una cadena alineada a la derecha que contiene la cadena especificada ajustada a la longitud especificada.|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios finales.|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Devuelve una cadena que consta del número especificado de espacios.|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Devuelve una matriz unidimensional de base cero que contiene un número especificado de subcadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Devuelve-1, 0 o 1, en función del resultado de una comparación de cadenas.|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Devuelve una cadena convertida según lo especificado.|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Devuelve una cadena o un objeto que se compone del carácter especificado repetido el número especificado de veces.|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Devuelve una cadena en la que se invierte el orden de los caracteres de una cadena especificada.|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales ni finales.|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Devuelve una cadena o un carácter que contiene la cadena especificada convertida en mayúsculas.|  
  
 Puede usar la instrucción [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) para establecer si las cadenas se comparan mediante un criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas determinado por la configuración regional del sistema (`Text`) o por las representaciones binarias internas de los caracteres (`Binary`). El método de comparación de texto predeterminado es `Binary`.  
  
## <a name="example-ucase"></a>Ejemplo: UCase

En este ejemplo se usa la función `UCase` para devolver una versión en mayúsculas de una cadena.  
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example-ltrim"></a>Ejemplo: LTrim

En este ejemplo se usa la función `LTrim` para quitar los espacios iniciales y la función `RTrim` para quitar los espacios finales de una variable de cadena. Usa la función `Trim` para quitar ambos tipos de espacios.  
  
[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example-mid"></a>Ejemplo: MID

En este ejemplo se usa la función `Mid` para devolver un número especificado de caracteres de una cadena.  

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  

## <a name="example-len"></a>Ejemplo: Len

En este ejemplo se usa `Len` para devolver el número de caracteres de una cadena.  
  
[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example-instr"></a>Ejemplo: InStr

En este ejemplo se usa la función `InStr` para devolver la posición de la primera aparición de una cadena dentro de otra.  
  
[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example-format"></a>Ejemplo: Format

En este ejemplo se muestran varios usos de la función `Format` para dar formato a los valores mediante formatos `String` y formatos definidos por el usuario. En el caso del separador de fecha (`/`), el separador de hora (`:`) y los indicadores de AM/PM (@no__t 2 y `tt`), la salida con formato real que muestra el sistema depende de la configuración regional que use el código. Cuando se muestran las horas y las fechas en el entorno de desarrollo, se usan el formato de hora corta y el formato de fecha corta de la configuración regional del código.  
  
> [!NOTE]
> En el caso de las configuraciones regionales que utilizan un reloj de 24 horas, los indicadores de AM/PM (`t` y `tt`) no muestran nada.  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>Vea también

- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
- [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../../../visual-basic/language-reference/runtime-library-members.md)
- [Resumen de manipulación de cadenas](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
- [System. String (métodos de clase)](xref:System.String#methods)
