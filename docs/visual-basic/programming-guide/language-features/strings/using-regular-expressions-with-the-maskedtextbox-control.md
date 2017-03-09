---
title: "Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "cadenas [Visual Basic], Masked Edit"
  - "cadenas [Visual Basic], expresiones regulares"
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Utilizar expresiones regulares con el control MaskedTextBox en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo muestra cómo convertir las expresiones regulares simples para trabajar con el control <xref:System.Windows.Forms.MaskedTextBox>.  
  
## Descripción del idioma de enmascarado  
 El lenguaje de enmascaramiento estándar de <xref:System.Windows.Forms.MaskedTextBox> se basa en el que usa el control `Masked Edit` de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 6.0 y debe resultarle familiar a los usuarios que migren desde esa plataforma.  
  
 La propiedad <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> del control <xref:System.Windows.Forms.MaskedTextBox> especifica qué máscara de entrada se debe utilizar.  La máscara debe ser una cadena compuesta de uno o más de los elementos de enmascarado contenidos en la tabla siguiente.  
  
|Elemento de enmascaramiento|Descripción|Elemento de expresión regular|  
|---------------------------------|-----------------|-----------------------------------|  
|0|Cualquier dígito único comprendido entre 0 y 9.  Entrada obligatoria.|\\d|  
|9|Dígito o espacio.  Entrada opcional.|\[ \\d\]?|  
|\#|Dígito o espacio.  Entrada opcional.  Si esta posición es el espacio en blanco izquierdo de la máscara, se representará como un espacio.  Se permiten los signos más \(\+\) y menos \(\-\).|\[ \\d\+\-\]?|  
|L|Letra ASCII.  Entrada obligatoria.|\[a\-zA\-Z\]|  
|?|Letra ASCII.  Entrada opcional.|\[a\-zA\-Z\]?|  
|&|Character.  Entrada obligatoria.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]|  
|C|Character.  Entrada opcional.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]?|  
|A|Alfanumérico.  Entrada opcional.|\\W|  
|.|Marcador de posición de decimales adecuado para la referencia cultural.|No disponible.|  
|,|Marcador de posición de separador de miles adecuado para la referencia cultural.|No disponible.|  
|:|Separador de hora adecuado para la referencia cultural.|No disponible.|  
|\/|Separador de fecha adecuado parala referencia cultural.|No disponible.|  
|$|Símbolo de moneda adecuado para la referencia cultural.|No disponible.|  
|\<|Convierte en minúsculas todos los caracteres que hay a continuación.|No disponible.|  
|\>|Convierte a mayúsculas todos los caracteres siguientes.|No disponible.|  
|&#124;|Deshace un cambio anterior a mayúsculas o minúsculas.|No disponible.|  
|\\|Convierte un carácter de la máscara en un literal. "  \\\\" es la secuencia de escape para una barra diagonal inversa.|\\|  
|Todos los demás caracteres.|Literales.  Todos los elementos no enmascarados aparecerán como tales dentro de <xref:System.Windows.Forms.MaskedTextBox>.|Todos los demás caracteres.|  
  
 Los símbolos decimal \(.\), de miles \(,\), de hora \(:\), de fecha \(\/\) y de moneda \($\) toman como valor predeterminado los definidos porla referencia cultural y de referencia cultural de la aplicación.  Puede forzarlos a que muestren los símbolos de otra referencia cultural utilizando la propiedad <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>.  
  
## Expresiones regulares y máscaras  
 Aunque puede utilizar expresiones regulares y máscaras para validar los datos proporcionados por el usuario, no son completamente equivalentes.  Las expresiones regulares pueden expresar modelos más complejos que los de las máscaras, pero las máscaras pueden expresar más sucintamente la misma información y en un formato adecuado a las referencias culturales.  
  
 La tabla siguiente compara cuatro expresiones regulares y la máscara equivalente a cada una.  
  
|Expresión regular|Máscara|Notas|  
|-----------------------|-------------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|El carácter `/` de la máscara es un separador de fecha lógico, y se presentará al usuario como el separador de fecha apropiado a las referencias culturales actuales de la aplicación.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|Una fecha \(día, abreviatura del mes y año\) en el formato de Estados Unidos, en el que se muestra la abreviatura de los meses con tres letras con una letra mayúscula inicial seguida por dos letras en minúscula.|  
|`(\(\d{3}\)-)?  \d{3}-d{4}`|`(999)-000-0000`|Número de teléfono de Estados Unidos, con código de área opcional.  Si el usuario no desea escribir los caracteres opcionales, puede escribir espacios o colocar el puntero del mouse directamente en la posición de la máscara representada por el primer 0.|  
|`$\d{6}.00`|`$999,999.00`|Un valor de divisa comprendido en el intervalo de 0 a 999999.  Los caracteres de divisa, separador de miles y separador de decimales se sustituirán en tiempo de ejecución por sus equivalentes específicos de la referencia cultural.|  
  
## Vea también  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>   
 <xref:System.Windows.Forms.MaskedTextBox>   
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)   
 [MaskedTextBox \(Control\)](../Topic/MaskedTextBox%20Control%20\(Windows%20Forms\).md)