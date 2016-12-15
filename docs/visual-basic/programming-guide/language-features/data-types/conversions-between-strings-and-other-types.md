---
title: "Conversiones entre cadenas y otros tipos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversiones, tipo de datos"
  - "conversiones, tipo"
  - "conversión de tipos de datos, cadena"
  - "configuración regional"
  - "conversión de cadenas"
  - "conversión de tipos, cadena"
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conversiones entre cadenas y otros tipos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los valores numéricos, `Boolean` o de fecha y hora pueden convertirse en un valor de tipo `String`.  También puede realizarse la conversión en la dirección inversa \(de un valor de cadena a un valor numérico, `Boolean` o `Date`\) siempre que el contenido de la cadena se pueda interpretar como un valor válido del tipo de datos de destino.  Si no es posible, se produce un error en tiempo de ejecución.  
  
 Las conversiones de todas estas asignaciones, en ambas direcciones, son conversiones de restricción.  Deben utilizarse las palabras clave de conversión de tipos \(`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort` y `CType`\).  Las funciones <xref:Microsoft.VisualBasic.Strings.Format%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A> proporcionan un control adicional sobre las conversiones entre cadenas y números.  
  
 Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de su clase o estructura.  Para obtener más información, vea [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## Conversión de números en cadenas  
 Puede utilizar la función `Format` para convertir un número en una cadena con formato, lo que puede incluir no solo los dígitos adecuados sin también símbolos de formato como un signo de divisa \(por ejemplo, `$`\), separadores de miles o *símbolos de agrupación de dígitos* \(por ejemplo, `,`\) y un separador de decimales \(por ejemplo, `.`\).  `Format` utiliza automáticamente los símbolos adecuados según la **Configuración regional** especificada en el **Panel de control** de Windows.  
  
 Tenga en cuenta que el operador de concatenación \(`&`\) puede convertir un número en una cadena de forma implícita, como se muestra en el ejemplo siguiente.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## Conversión de cadenas en números  
 Puede usar la función `Val` para convertir de forma explícita los dígitos de una cadena en un número.  `Val` lee la cadena hasta que encuentre un carácter distinto de un dígito, un espacio, una pestaña, un salto de línea o un punto.  Las secuencias “&O” y “&H” alteran la base del sistema numérico y finalizan el examen.  Hasta que finaliza la lectura, `Val` convierte todos los caracteres apropiados en un valor numérico.  Por ejemplo, la instrucción siguiente devuelve el valor `141.825`.  
  
 `Val("   14   1.825 miles")`  
  
 Cuando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] convierte una cadena en un valor numérico, usa los valores especificados en la **Configuración regional** del **Panel de control** de Windows para interpretar el separador de miles, el separador decimal y el símbolo de moneda.  Esto significa que una conversión puede realizarse correctamente bajo una configuración, pero no bajo otra.  Por ejemplo, `"$14.20"` es aceptable en la configuración regional de inglés \(Estados Unidos\), pero no en la de francés.  
  
## Vea también  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Cómo: Convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Introducción a aplicaciones internacionales basadas en .NET Framework](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)