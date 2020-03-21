---
title: Uso de expresiones regulares con el control MaskedTextBox
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: b997f6f495fca51e888bb995fee0361d29d68048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148289"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
En este ejemplo se muestra cómo convertir <xref:System.Windows.Forms.MaskedTextBox> expresiones regulares simples para trabajar con el control.  
  
## <a name="description-of-the-masking-language"></a>Descripción del lenguaje enmascarado  
 El <xref:System.Windows.Forms.MaskedTextBox> lenguaje de enmascaramiento estándar se `Masked Edit` basa en el utilizado por el control en Visual Basic 6.0 y debe ser familiar para los usuarios que migran desde esa plataforma.  
  
 La <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad <xref:System.Windows.Forms.MaskedTextBox> del control especifica qué máscara de entrada se va a utilizar. La máscara debe ser una cadena compuesta por uno o varios de los elementos de enmascaramiento de la tabla siguiente.  
  
|Elemento de enmascaramiento|Descripción|Elemento de expresión regular|  
|---------------------|-----------------|--------------------------------|  
|0|Cualquier dígito único entre 0 y 9. Se requiere entrada.|\d|  
|9|Dígito o espacio. Entrada opcional.|[d]?|  
|#|Dígito o espacio. Entrada opcional. Si esta posición se deja en blanco en la máscara, se representará como un espacio. Se permiten signos más (+) y menos (-).|[d+-]?|  
|L|Carta ASCII. Se requiere entrada.|[a-zA-Z]|  
|?|Carta ASCII. Entrada opcional.|[a-zA-Z]?|  
|&|Carácter. Se requiere entrada.|['p'Ll'''''Lu''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''|  
|C|Carácter. Entrada opcional.|['p'Ll''''Lu''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''''|  
|Un|Alfanuméricos. Entrada opcional.|\W|  
|.|Marcador de posición decimal apropiado para la referencia cultural.|No disponible.|  
|,|Marcador de posición de miles apropiado para la cultura.|No disponible.|  
|:|Separador de tiempo apropiado para la cultura.|No disponible.|  
|/|Separador de fecha apropiado para la referencia cultural.|No disponible.|  
|$|Símbolo de moneda apropiado para la cultura.|No disponible.|  
|\<|Convierte todos los caracteres que siguen a minúsculas.|No disponible.|  
|>|Convierte todos los caracteres que siguen a mayúsculas.|No disponible.|  
|&#124;|Deshace un cambio anterior hacia arriba o hacia abajo.|No disponible.|  
|&#92;|Escapa de un carácter de máscara, convirtiéndolo en un literal. "\\\\" es la secuencia de escape de una barra diagonal inversa.|&#92;|  
|Todos los demás personajes.|Literales. Todos los elementos que no <xref:System.Windows.Forms.MaskedTextBox>sean máscara aparecerán como ellos mismos dentro de .|Todos los demás personajes.|  
  
 Los símbolos decimal (.), milésimas (,), hora (:), fecha (/) y moneda ($) muestran de forma predeterminada esos símbolos según lo definido por la referencia cultural de la aplicación. Puede forzarlos a mostrar símbolos para <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> otra referencia cultural mediante la propiedad.  
  
## <a name="regular-expressions-and-masks"></a>Expresiones regulares y máscaras  
 Aunque puede usar expresiones regulares y máscaras para validar la entrada del usuario, no son completamente equivalentes. Las expresiones regulares pueden expresar patrones más complejos que las máscaras, pero las máscaras pueden expresar la misma información de forma más sucinta y en un formato culturalmente relevante.  
  
 En la tabla siguiente se comparan cuatro expresiones regulares y la máscara equivalente para cada una.  
  
|Expresión regular|Máscara|Notas|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El `/` carácter de la máscara es un separador de fecha lógico y aparecerá al usuario como el separador de fecha adecuado a la referencia cultural actual de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha (día, abreviatura de mes y año) en formato de Estados Unidos en la que la abreviatura de mes de tres letras se muestra con una letra mayúscula inicial seguida de dos letras minúsculas.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Número de teléfono de Los Estados Unidos, código de área opcional. Si el usuario no desea introducir los caracteres opcionales, puede introducir espacios o colocar el puntero del ratón directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valor de moneda en el rango de 0 a 999999. Los caracteres de moneda, milésima y decimal se reemplazarán en tiempo de ejecución con sus equivalentes específicos de la referencia cultural.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [Control MaskedTextBox](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
