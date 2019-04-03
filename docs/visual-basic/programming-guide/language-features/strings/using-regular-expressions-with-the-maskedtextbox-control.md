---
title: Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: e0165fb8d573878ae19378b2656d89627680b804
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826753"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
En este ejemplo se muestra cómo convertir las expresiones regulares simples para trabajar con el <xref:System.Windows.Forms.MaskedTextBox> control.  
  
## <a name="description-of-the-masking-language"></a>Descripción del lenguaje de enmascaramiento  
 El estándar <xref:System.Windows.Forms.MaskedTextBox> lenguaje de enmascaramiento se basa en lo que se usa el `Masked Edit` controlar en Visual Basic 6.0 y debería resultar familiar a los usuarios que migren desde esa plataforma.  
  
 El <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad de la <xref:System.Windows.Forms.MaskedTextBox> control especifica qué máscara de entrada que se utilizará. La máscara debe ser una cadena compuesta de uno o varios de los elementos de enmascaramiento de la tabla siguiente.  
  
|Elemento de enmascaramiento|Descripción|Elemento de expresión regular|  
|---------------------|-----------------|--------------------------------|  
|0|Cualquier dígito comprendido entre 0 y 9. Entrada requerida.|\d|  
|9|Dígito o espacio. Entrada opcional.|[ \d]?|  
|#|Dígito o espacio. Entrada opcional. Si esta posición se deja en blanco en la máscara, se representará como un espacio. Signo más (+) y menos (-) se permiten signos.|[ \d+-]?|  
|L|Letra ASCII. Entrada requerida.|[a-zA-Z]|  
|?|Letra ASCII. Entrada opcional.|¿[a-zA-Z]?|  
|&|Carácter. Entrada requerida.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carácter. Entrada opcional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfanumérico. Entrada opcional.|\W|  
|.|Marcador de posición decimal adecuado para la referencia cultural.|No está disponible.|  
|,|Marcador de posición miles adecuado para la referencia cultural.|No está disponible.|  
|:|Separador de hora adecuado para la referencia cultural.|No está disponible.|  
|/|Separador de fecha adecuado para la referencia cultural.|No está disponible.|  
|$|Símbolo de divisa adecuado según la referencia cultural.|No está disponible.|  
|\<|Convierte todos los caracteres que siguen a minúsculas.|No está disponible.|  
|>|Convierte todos los caracteres que siguen a mayúsculas.|No está disponible.|  
|&#124;|Deshace un cambio anterior de mayúsculas o minúsculas.|No está disponible.|  
|&#92;|Convierte un carácter de máscara, convirtiéndolo en un literal. "\\\\" es la secuencia de escape para una barra diagonal inversa.|&#92;|  
|Todos los demás caracteres.|Literales. Todos los elementos de máscara no aparecerán como ellos mismos en <xref:System.Windows.Forms.MaskedTextBox>.|Todos los demás caracteres.|  
  
 El separador decimal (.), miles (,), hora (:), fecha (/) y predeterminada de los símbolos de moneda ($) para mostrar esos símbolos definidos por la referencia cultural de la aplicación. Puede obligarlos a mostrar los símbolos para otra referencia cultural mediante la <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> propiedad.  
  
## <a name="regular-expressions-and-masks"></a>Expresiones regulares y máscaras  
 Aunque puede utilizar expresiones regulares y máscaras para validar la entrada del usuario, no son completamente equivalentes. Expresiones regulares pueden expresar modelos más complejos que las máscaras, pero las máscaras pueden expresar la misma información de forma más sucinta y en un formato de referencia cultural pertinente.  
  
 En la tabla siguiente compara las cuatro expresiones regulares y la máscara equivalente para cada uno.  
  
|Expresión regular|Máscara|Notas|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El `/` en la máscara es un separador de fecha lógica, y aparecerá al usuario como el separador de fecha adecuado para la referencia cultural actual de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha (día, abreviatura del mes y año) en formato de Estados Unidos en el que se muestra la abreviatura del mes de tres letras con una letra mayúscula inicial seguida de dos letras en minúsculas.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Número de teléfono de Estados Unidos, código de área opcional. Si el usuario no desea escribir los caracteres opcionales, puede escribir espacios o colocar el puntero del mouse directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valor de moneda en el intervalo de 0 a 999999. La moneda, milésima de segundo y caracteres decimales se reemplazará en tiempo de ejecución con sus equivalentes específicos de la referencia cultural.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [MaskedTextBox (control)](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
