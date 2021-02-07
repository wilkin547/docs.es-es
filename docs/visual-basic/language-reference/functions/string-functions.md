---
description: 'Más información sobre: funciones de cadena (Visual Basic)'
title: Funciones de cadena
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 1c121bc3de66caf748426b5cd04d049b30bf78bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731157"
---
# <a name="string-functions-visual-basic"></a>Funciones de cadena (Visual Basic)

En la tabla siguiente se enumeran las funciones que Visual Basic proporciona en la <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType> clase para buscar y manipular cadenas. Se pueden considerar como Visual Basic funciones intrínsecas; es decir, no tiene que llamarlos como miembros explícitos de una clase, como se muestra en los ejemplos. Los métodos adicionales y, en algunos casos, métodos complementarios, están disponibles en la <xref:System.String?displayProperty=nameWithType> clase.

|Método .NET Framework|Descripción|
|---------------------------|-----------------|
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|Devuelve un `Integer` valor que representa el código de carácter correspondiente a un carácter.|
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|Devuelve el carácter asociado al código de carácter especificado.|
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|Devuelve una matriz basada en cero que contiene un subconjunto de una matriz `String` basada en criterios de filtro especificados.|
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|Devuelve una cadena con el formato que especifiquen las instrucciones contenidas en una expresión `String` de formato.|
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|Devuelve una expresión con formato de moneda en la que se utilizará el símbolo de moneda que se haya definido en el panel de control del sistema.|
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|Devuelve una expresión de cadena que representa un valor de fecha u hora.|
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|Devuelve una expresión con formato de número.|
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|Devuelve una expresión con formato de porcentaje (es decir, multiplicada por 100) con un carácter % final.|
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|Devuelve un entero que especifica la posición inicial de la primera aparición de una cadena dentro de otra.|
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|Devuelve la posición de la primera aparición de una cadena dentro de otra, comenzando por el extremo derecho de la cadena.|
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|Devuelve una cadena creada a partir de la combinación de varias subcadenas contenidas en una matriz.|
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|Devuelve una cadena o un carácter convertidos en minúscula.|
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|Devuelve una cadena que contiene un número especificado de caracteres a partir del lado izquierdo de una cadena.|
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|Devuelve un entero que contiene el número de caracteres de una cadena.|
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|Devuelve una cadena alineada a la izquierda que contiene la cadena especificada ajustada a la longitud indicada.|
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales.|
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|Devuelve una cadena que contiene un número especificado de caracteres de una cadena.|
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|Devuelve una cadena en la que la subcadena especificada se reemplaza determinado número de veces por otra subcadena.|
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|Devuelve una cadena que contiene un número especificado de caracteres desde el lado derecho de una cadena.|
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|Devuelve una cadena alineada a la derecha que contiene la cadena especificada y con la longitud especificada.|
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios finales.|
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|Devuelve una cadena que consta del número especificado de espacios.|
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|Devuelve una matriz unidimensional basada en cero que contiene un número especificado de subcadenas.|
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|Devuelve un valor, -1, 0 ó 1, que indica el resultado de una comparación de cadena.|
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|Devuelve una cadena convertida según se ha especificado.|
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|Devuelve una cadena o un objeto que se compone del carácter especificado repetido el número de veces especificado.|
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|Devuelve una cadena en la que se invierte el orden de los caracteres de la cadena especificada.|
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|Devuelve una cadena que contiene una copia de una cadena especificada sin espacios iniciales ni finales.|
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|Devuelve una cadena o un carácter que contiene la cadena especificada convertida en mayúsculas.|

Puede usar la instrucción [Option Compare](../statements/option-compare-statement.md) para establecer si las cadenas se comparan mediante un criterio de ordenación de texto sin distinción entre mayúsculas y minúsculas determinado por la configuración regional del sistema ( `Text` ) o por las representaciones binarias internas de los caracteres ( `Binary` ). El método de comparación de texto predeterminado es `Binary`.

## <a name="example-ucase"></a>Ejemplo: UCase

En este ejemplo se utiliza la función `UCase` para devolver la versión en mayúsculas de una cadena.
[!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]

## <a name="example-ltrim"></a>Ejemplo: LTrim

En este ejemplo se usa la función `LTrim` para quitar los espacios iniciales y la función `RTrim` para quitar los espacios finales de una variable de cadena. También se usa la función `Trim` para quitar ambos tipos de espacios.

[!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]

## <a name="example-mid"></a>Ejemplo: MID

En este ejemplo se utiliza la `Mid` función para devolver un número especificado de caracteres de una cadena.

[!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]

## <a name="example-len"></a>Ejemplo: Len

En este ejemplo se utiliza `Len` para devolver el número de caracteres de una cadena:

[!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]

## <a name="example-instr"></a>Ejemplo: InStr

En este ejemplo se usa la función `InStr` para devolver la posición de la primera aparición de una cadena dentro de otra.

[!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]

## <a name="example-format"></a>Ejemplo: Format

En este ejemplo se muestran los diversos usos de la función `Format` para dar formato a valores tanto con formatos `String` como otros definidos por el usuario. Para el separador de fecha (`/`), hora (`:`) e indicadores de a.m./p.m. (`t` y `tt`), el formato de salida que muestre su sistema dependerá de la configuración regional que use el código. Cuando las horas y fechas se muestren en el entorno de desarrollo, se utilizará el formato de fecha y hora corta de la configuración regional del código.

> [!NOTE]
> Para configuraciones regionales que utilizan un reloj de 24 horas, los indicadores de a.m./p.m. (`t` y `tt`) no muestran nada.

[!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]

## <a name="see-also"></a>Vea también

- [Palabras clave](../keywords/index.md)
- [Miembros de la biblioteca en tiempo de ejecución de Visual Basic](../runtime-library-members.md)
- [Resumen de la manipulación de cadenas](../keywords/string-manipulation-summary.md)
- [System. String (métodos de clase)](xref:System.String#methods)
