---
title: Utilizar expresiones regulares con el Control MaskedTextBox en Visual Basic | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 15d8f131aa834321fcf7e8ca633929385c666e6a
ms.lasthandoff: 03/13/2017

---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
En este ejemplo se muestra cómo convertir las expresiones regulares simples para trabajar con el <xref:System.Windows.Forms.MaskedTextBox>control.</xref:System.Windows.Forms.MaskedTextBox>  
  
## <a name="description-of-the-masking-language"></a>Descripción del lenguaje de enmascaramiento  
 El estándar <xref:System.Windows.Forms.MaskedTextBox>lenguaje de enmascaramiento se basa en el usado por el `Masked Edit` del control de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0 y debe resultarle familiar a los usuarios que migren desde esa plataforma.</xref:System.Windows.Forms.MaskedTextBox>  
  
 El <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>propiedad de la <xref:System.Windows.Forms.MaskedTextBox>control especifica qué máscara de entrada que utilice.</xref:System.Windows.Forms.MaskedTextBox> </xref:System.Windows.Forms.MaskedTextBox.Mask%2A> La máscara debe ser una cadena compuesta de uno o varios de los elementos de enmascaramiento de la tabla siguiente.  
  
|Elemento de enmascaramiento|Descripción|Elemento de expresión regular|  
|---------------------|-----------------|--------------------------------|  
|0|Cualquier dígito único entre 0 y 9. Entrada requerida.|\d|  
|9|Dígito o espacio. Entrada opcional.|[ \d]?|  
|#|Dígito o espacio. Entrada opcional. Si esta posición está en blanco en la máscara, se representará como un espacio. Signo más (+) y menos (-) se permiten signos.|[ \d+-]?|  
|L|Letra ASCII. Entrada requerida.|[a-zA-Z]|  
|?|Letra ASCII. Entrada opcional.|¿[a-zA-Z]?|  
|&|Carácter. Entrada requerida.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo]}|  
|C|Carácter. Entrada opcional.|¿[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfanumérico. Entrada opcional.|\W|  
|.|Marcador de posición decimal adecuado para la referencia cultural.|No está disponible.|  
|,|Marcador de posición de miles adecuado para la referencia cultural.|No está disponible.|  
|:|Separador de hora adecuado para la referencia cultural.|No está disponible.|  
|/|Separador de fecha adecuado para la referencia cultural.|No está disponible.|  
|$|Símbolo de moneda adecuado para la referencia cultural.|No está disponible.|  
|\<|Convierte todos los caracteres que siguen a minúsculas.|No está disponible.|  
|>|Convierte todos los caracteres que siguen a mayúsculas.|No está disponible.|  
|&#124;|Deshace un cambio anterior de mayúsculas o minúsculas.|No está disponible.|  
|\|Convierte un carácter de máscara, convirtiéndolo en un literal. "\\\\" es la secuencia de escape para una barra diagonal inversa.|\|  
|Todos los demás caracteres.|Literales. Todos los elementos no enmascarados aparecerán como ellos mismos <xref:System.Windows.Forms.MaskedTextBox>.</xref:System.Windows.Forms.MaskedTextBox>|Todos los demás caracteres.|  
  
 El separador decimal (.), miles (,), hora (:), fecha (/) y predeterminada de símbolos de moneda ($) para mostrar los símbolos de acuerdo con la referencia cultural de la aplicación. Puede forzar que muestren los símbolos de otra referencia cultural utilizando el <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>propiedad.</xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>  
  
## <a name="regular-expressions-and-masks"></a>Expresiones regulares y máscaras  
 Aunque puede utilizar expresiones regulares y máscaras para validar la entrada del usuario, no son totalmente equivalentes. Las expresiones regulares pueden expresar modelos más complejos de máscaras, pero máscaras pueden expresar la misma información de forma más concisa y en un formato de referencia cultural correspondiente.  
  
 La tabla siguiente compara cuatro expresiones regulares y la máscara equivalente para cada uno.  
  
|Expresión regular|Máscara|Notas|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El `/` de la máscara es un separador de fecha lógico y aparecerá al usuario como el separador de fecha adecuado para la referencia cultural actual de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha (día, abreviatura del mes y año) en formato de Estados Unidos en el que se muestra la abreviatura del mes de tres letras con una letra mayúscula inicial seguida de dos letras en minúsculas.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Número de teléfono de Estados Unidos, código de área opcional. Si el usuario no desea escribir los caracteres opcionales, ella puede escribir espacios o colocar el puntero del mouse directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Valor de moneda en el intervalo de 0 a 999999. La moneda y milésima caracteres decimales se sustituirán en tiempo de ejecución con sus equivalentes específicos de la referencia cultural.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A></xref:System.Windows.Forms.MaskedTextBox.Mask%2A>   
 <xref:System.Windows.Forms.MaskedTextBox></xref:System.Windows.Forms.MaskedTextBox>   
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)   
 [MaskedTextBox (Control)](http://msdn.microsoft.com/library/235d6121-027d-481d-8d59-4f6794d15d0c)
