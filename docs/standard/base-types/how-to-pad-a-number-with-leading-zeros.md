---
title: "C&#243;mo: Rellenar un n&#250;mero con ceros iniciales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dar formato [.NET Framework], números"
  - "dar formato a números [.NET Framework]"
  - "números [.NET Framework], cadenas de formato"
  - "cadenas de formato numérico [.NET Framework]"
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Rellenar un n&#250;mero con ceros iniciales
Si desea agregar ceros a la izquierda de un entero, puede hacerlo mediante la [cadena de formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md)“D” con un especificador de precisión.  Para agregar ceros a la izquierda tanto de enteros como de números de punto flotante, use una [cadena de formato numérico estándar](../../../docs/standard/base-types/custom-numeric-format-strings.md).  En este tema se explica cómo usar ambos métodos para rellenar un número con ceros a la izquierda.  
  
### Para rellenar un entero con ceros a la izquierda hasta una longitud concreta  
  
1.  Determine el número mínimo de dígitos que desea que muestre el valor entero.  Incluya los dígitos a la izquierda en este número.  
  
2.  Determine si desea mostrar el entero como valor decimal o hexadecimal.  
  
    -   Para mostrar el entero como valor decimal, llame a su método `ToString(String)` y pase la cadena “D*n*” como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.  
  
    -   Para mostrar el entero como valor hexadecimal, llame a su método `ToString(String)` y pase la cadena “X*n*” como valor del parámetro `format`, donde *n* representa la longitud mínima de la cadena.  
  
     También puede usar la cadena de formato en un método como, por ejemplo, <xref:System.String.Format%2A> o <xref:System.Console.WriteLine%2A>, que usan [formato compuesto](../../../docs/standard/base-types/composite-formatting.md).  
  
 En el ejemplo siguiente se aplica formato a varios valores enteros con ceros a la izquierda de modo que la longitud mínima total del número con formato sea de ocho caracteres.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### Para rellenar un entero con una determinada cantidad de ceros a la izquierda  
  
1.  Determine cuántos ceros a la izquierda desea que muestre el valor entero.  
  
2.  Determine si desea mostrar el entero como valor decimal o hexadecimal.  Para aplicar el formato de valor decimal hay que usar el especificador de formato estándar “D”, mientras que para el valor hexadecimal hay que usar el especificador de formato estándar “X”.  
  
3.  Determine la longitud de la cadena numérica sin rellenar mediante una llamada a los métodos `ToString("D").Length` o `ToString("X").Length` del valor entero.  
  
4.  Agregue el número de ceros a la izquierda que desea incluir en la cadena con formato a la longitud de la cadena numérica sin rellenar.  Esto define la longitud total de la cadena rellenada.  
  
5.  Llame al método `ToString(String)` del valor entero y pase la cadena “D*n*” para cadenas decimales y “X*n*” para cadenas hexadecimales, donde *n* representa la longitud total de la cadena rellenada.  También puede usar la cadena de formato “D*n*” o “X*n*” en un método que admita formato compuesto.  
  
 En el ejemplo siguiente se rellena un valor entero con cinco ceros a la izquierda.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### Para rellenar un valor numérico con ceros a la izquierda hasta una longitud concreta  
  
1.  Determine con cuántos dígitos a la izquierda del decimal desea que se represente la cadena del número.  Incluya los ceros a la izquierda en este número total de dígitos.  
  
2.  Defina una cadena de formato numérico personalizado en la que se use el marcador de posición cero \(“0”\) para representar el número mínimo de ceros.  
  
3.  Llame al método `ToString(String)` del número y pase la cadena de formato personalizado.  También puede usar la cadena de formato personalizado con un método que admita formato compuesto.  
  
 En el ejemplo siguiente se aplica formato a varios valores numéricos con ceros a la izquierda de modo que la longitud total del número con formato sea de al menos ocho dígitos a la izquierda del decimal.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### Para rellenar un valor numérico con una determinada cantidad de ceros a la izquierda  
  
1.  Determine cuántos ceros a la izquierda desea que tenga el valor numérico.  
  
2.  Determine el número de dígitos a la izquierda del decimal que tendrá la cadena numérica sin rellenar.  Para hacerlo:  
  
    1.  Determine si la representación de cadena de un número incluye un símbolo de separador decimal.  
  
    2.  Si incluye un símbolo de separador decimal, determine el número de caracteres a la izquierda del separador decimal.  
  
         O bien  
  
         Si no incluye un símbolo de separador decimal, determine la longitud de la cadena.  
  
3.  Cree una cadena de formato personalizado en la que se use el marcador de posición cero \(“0”\) para cada uno de los ceros a la izquierda que aparecen en la cadena, y en la que se use también el marcador de posición cero o el marcador de posición de dígitos \(“\#”\) para representar cada uno de los dígitos de la cadena predeterminada.  
  
4.  Proporcione la cadena de formato personalizado como un parámetro bien al método `ToString(String)` del número, bien a un método que admita el formato compuesto.  
  
 En el ejemplo siguiente se rellenan dos valores <xref:System.Double> con cinco ceros a la izquierda.  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## Vea también  
 [Cadenas con formato numérico personalizado](../../../docs/standard/base-types/custom-numeric-format-strings.md)   
 [Cadenas con formato numérico estándar](../../../docs/standard/base-types/standard-numeric-format-strings.md)   
 [Formatos compuestos](../../../docs/standard/base-types/composite-formatting.md)