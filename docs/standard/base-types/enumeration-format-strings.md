---
title: "Cadenas de formato de enumeraci&#243;n | Microsoft Docs"
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
  - "cadenas de formato de enumeración"
  - "especificadores de formato, cadenas de formato de enumeración"
  - "dar formato [.NET Framework], enumeración"
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Cadenas de formato de enumeraci&#243;n
Puede utilizar el método <xref:System.Enum.ToString%2A?displayProperty=fullName> para crear un nuevo objeto de cadena que represente un valor numérico, hexadecimal o de cadena de un miembro de la enumeración.  Este método toma una de las cadenas que dan formato a la enumeración para especificar el valor que se desea que se devuelva.  
  
 En la siguiente tabla se enumeran las cadenas que dan formato a la enumeración y los valores que devuelven.  Estos especificadores de formato no hacen distinción entre mayúsculas y minúsculas.  
  
|Cadena de formato|Resultado|  
|-----------------------|---------------|  
|G o g|Muestra la entrada de la enumeración como un valor de cadena, si es posible, y en caso contrario, muestra el valor de entero de la instancia actual.  Si la enumeración se define con el conjunto de atributos **Flags**, los valores de cadena de cada entrada válida se concatenan juntos, separados por comas.  Si no está establecido el atributo **Flags**, se muestra un valor no válido como una entrada numérica.  En el ejemplo siguiente se muestra el especificador de formato G.<br /><br /> [!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)]
 [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)]|  
|F o f|Muestra la entrada de enumeración como un valor de cadena si es posible.  Si el valor se puede mostrar por completo como una sumatoria de las entradas de la enumeración \(incluso si no está presente el atributo **Flags\)**, los valores de cadena de cada entrada válida se concatenan juntos, separados por comas.  Si el valor no se puede determinar completamente con las entradas de la enumeración, entonces se le da formato al valor como valor de entero.  En el ejemplo siguiente se muestra el especificador de formato F.<br /><br /> [!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)]
 [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)]|  
|D o d|Muestra la entrada de enumeración como un valor de entero de la representación más corta posible.  En el ejemplo siguiente se muestra el especificador de formato D.<br /><br /> [!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)]
 [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)]|  
|X o x|Presenta la entrada de la enumeración como un valor hexadecimal.  El valor se representa con tantos ceros iniciales como sea necesario para asegurar que el valor tenga un largo mínimo de ocho dígitos.  En el ejemplo siguiente se muestra el especificador de formato X.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)]
 [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)]|  
  
## Ejemplo  
 En el ejemplo siguiente se define una enumeración denominada `Colors` que se compone de tres entradas: `Red`, `Blue` y `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 Una vez definida la enumeración, se declara una instancia de la manera siguiente.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 El método `Color.ToString(System.String)` se puede utilizar a continuación para mostrar el valor de enumeración de maneras diferentes, en función del especificador de formato que se le ha pasado.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## Vea también  
 [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md)