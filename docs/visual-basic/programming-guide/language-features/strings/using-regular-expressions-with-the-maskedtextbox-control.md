---
title: Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72542c05123ef62a8f95afbe1bb19cb823d1f21
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
En este ejemplo se muestra cómo convertir las expresiones regulares simples para trabajar con el <xref:System.Windows.Forms.MaskedTextBox> control.  
  
## <a name="description-of-the-masking-language"></a>Descripción del lenguaje de enmascaramiento  
 El estándar <xref:System.Windows.Forms.MaskedTextBox> lenguaje de enmascaramiento se basa en utilizado por el `Masked Edit` controlar en Visual Basic 6.0 y debe resultarle familiar a los usuarios que migren desde esa plataforma.  
  
 El <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> propiedad de la <xref:System.Windows.Forms.MaskedTextBox> control especifica qué máscara de entrada para usar. La máscara debe ser una cadena compuesta de uno o varios de los elementos de enmascaramiento de la tabla siguiente.  
  
|Elemento de enmascaramiento|Descripción|Elemento de expresión regular|  
|---------------------|-----------------|--------------------------------|  
|0|Cualquier dígito comprendido entre 0 y 9. Entrada requerida.|\d|  
|9|Dígito o espacio. Entrada opcional.|¿[\d]?|  
|#|Dígito o espacio. Entrada opcional. Si esta posición se deja en blanco en la máscara, se representará como un espacio. Signo más (+) y menos (-) se permiten signos.|¿[\d+-]?|  
|L|Letra ASCII. Entrada requerida.|[a-zA-Z]|  
|?|Letra ASCII. Entrada opcional.|¿[a-zA-Z]?|  
|&|Carácter. Entrada requerida.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|Carácter. Entrada opcional.|¿[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|Alfanumérico. Entrada opcional.|\W|  
|.|Marcador de posición decimal adecuado para la referencia cultural.|No está disponible.|  
|,|Marcador de posición de miles adecuado para la referencia cultural.|No está disponible.|  
|:|Separador de hora adecuado para la referencia cultural.|No está disponible.|  
|/|Separador de fecha adecuado para la referencia cultural.|No está disponible.|  
|$|Símbolo de moneda adecuado para la referencia cultural.|No está disponible.|  
|\<|Convierte todos los caracteres que siguen a minúsculas.|No está disponible.|  
|>|Convierte todos los caracteres que siguen a mayúsculas.|No está disponible.|  
|&#124;|Deshace un cambio anterior una o desplazar hacia abajo.|No está disponible.|  
|\|Convierte un carácter de máscara, convirtiéndolo en un literal. "\\\\" es la secuencia de escape para una barra diagonal inversa.|\|  
|Todos los demás caracteres.|Literales. Todos los elementos de la máscara no aparecerán como ellos mismos en <xref:System.Windows.Forms.MaskedTextBox>.|Todos los demás caracteres.|  
  
 El separador decimal (.), miles (,), hora (:), fecha (/) y predeterminada de símbolos de moneda ($) para mostrar esos símbolos tal como se define en la referencia cultural de la aplicación. Puede forzar que se muestren símbolos para otra referencia cultural utilizando el <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> propiedad.  
  
## <a name="regular-expressions-and-masks"></a>Expresiones regulares y máscaras  
 Aunque puede usar expresiones regulares y máscaras para validar entrada de usuario, no son totalmente equivalentes. Las expresiones regulares pueden expresar modelos más complejos de máscaras, pero máscaras pueden expresar la misma información más sucinta y en un formato de referencia cultural relevante.  
  
 En la tabla siguiente compara cuatro expresiones regulares y la máscara equivalente para cada uno.  
  
|Expresión regular|Máscara|Notas|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El `/` carácter en la máscara es un separador de fecha lógico y aparecerá al usuario como el separador de fecha apropiado para la referencia cultural actual de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha (día, abreviatura del mes y año) en formato de Estados Unidos en el que se muestra la abreviatura del mes de tres letras con una letra mayúscula inicial seguida de dos letras en minúsculas.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|Número de teléfono de Estados Unidos, código de área opcional. Si el usuario no desea escribir los caracteres opcionales, puede escribir espacios o colocar el puntero del mouse directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valor de moneda en el intervalo de 0 a 999999. La moneda, milésima de segundo y caracteres decimales se sustituirán en tiempo de ejecución con sus equivalentes específicos de la referencia cultural.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [MaskedTextBox (control)](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
