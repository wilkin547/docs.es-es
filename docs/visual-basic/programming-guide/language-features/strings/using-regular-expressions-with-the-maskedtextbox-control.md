---
description: 'Más información sobre: usar expresiones regulares con el control MaskedTextBox en Visual Basic'
title: Uso de expresiones regulares con el control MaskedTextBox
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: 68ffca6761d8f0634634ea2755786d3c0c02a6e2
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471141"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic

En este ejemplo se muestra cómo convertir expresiones regulares simples para trabajar con el <xref:System.Windows.Forms.MaskedTextBox> control.  
  
## <a name="description-of-the-masking-language"></a>Descripción del lenguaje de enmascaramiento  

 El <xref:System.Windows.Forms.MaskedTextBox> lenguaje de enmascaramiento estándar se basa en el que usa el `Masked Edit` control en Visual Basic 6,0 y debe estar familiarizado con los usuarios que migran desde esa plataforma.  
  
 La <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad del <xref:System.Windows.Forms.MaskedTextBox> control especifica la máscara de entrada que se va a usar. La máscara debe ser una cadena formada por uno o varios de los elementos de enmascaramiento de la tabla siguiente.  
  
|Enmascaramiento (elemento)|Descripción|Elemento de expresión regular|  
|---------------------|-----------------|--------------------------------|  
|0|Cualquier dígito individual entre 0 y 9. Entrada necesaria.|\d|  
|9|Dígito o espacio. Entry opcional.|[\d]?|  
|#|Dígito o espacio. Entry opcional. Si esta posición se deja en blanco en la máscara, se representará como un espacio. Se permiten signos más (+) y menos (-).|[\d +-]?|  
|L|Letra ASCII. Entrada necesaria.|[a-zA-Z]|  
|?|Letra ASCII. Entry opcional.|[a-zA-Z]?|  
|&|Carácter. Entrada necesaria.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carácter. Entry opcional.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfabético. Entry opcional.|\W|  
|.|Marcador de posición decimal apropiado para la referencia cultural.|No disponible.|  
|,|Marcador de posición de miles apropiado para la referencia cultural.|No disponible.|  
|:|Separador de hora correspondiente a la referencia cultural.|No disponible.|  
|/|El separador de fecha correspondiente a la referencia cultural.|No disponible.|  
|$|Símbolo de moneda apropiado para la referencia cultural.|No disponible.|  
|\<|Convierte todos los caracteres que siguen a minúsculas.|No disponible.|  
|>|Convierte todos los caracteres que siguen a mayúsculas.|No disponible.|  
|&#124;|Deshace el desplazamiento anterior o el desplazamiento hacia abajo.|No disponible.|  
|&#92;|Escapa un carácter de máscara, convirtiéndolo en un literal. " \\ \\ " es la secuencia de escape para una barra diagonal inversa.|&#92;|  
|Todos los demás caracteres.|Literales. Todos los elementos que no son de máscara aparecerán como ellos mismos en <xref:System.Windows.Forms.MaskedTextBox> .|Todos los demás caracteres.|  
  
 Los símbolos decimales (.), milésimas (,), Time (:), Date (/) y Currency ($) tienen como valor predeterminado los símbolos definidos por la referencia cultural de la aplicación. Puede obligarles a mostrar símbolos para otra referencia cultural utilizando la <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> propiedad.  
  
## <a name="regular-expressions-and-masks"></a>Expresiones regulares y máscaras  

 Aunque puede usar expresiones regulares y máscaras para validar la entrada del usuario, no son totalmente equivalentes. Las expresiones regulares pueden expresar patrones más complejos que las máscaras, pero las máscaras pueden expresar la misma información de forma más concisa y en un formato culturalmente relevante.  
  
 En la tabla siguiente se comparan cuatro expresiones regulares y la máscara equivalente para cada una de ellas.  
  
|Expresión regular|Máscara|Notas|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El `/` carácter de la máscara es un separador de fecha lógico y se mostrará al usuario como el separador de fecha apropiado para la referencia cultural actual de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha (día, abreviatura del mes y año) en Estados Unidos formato en el que se muestra la abreviatura del mes de tres letras con una letra mayúscula inicial seguida de dos letras en minúsculas.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Estados Unidos número de teléfono, código de área opcional. Si el usuario no desea escribir los caracteres opcionales, puede escribir espacios o colocar el puntero del mouse directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valor de moneda en el intervalo de 0 a 999999. Los caracteres Currency, milésima y decimal se reemplazarán en tiempo de ejecución por sus equivalentes específicos de la referencia cultural.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [Validar cadenas en Visual Basic](validating-strings.md)
- [Control MaskedTextBox](/dotnet/desktop/winforms/controls/maskedtextbox-control-windows-forms)
