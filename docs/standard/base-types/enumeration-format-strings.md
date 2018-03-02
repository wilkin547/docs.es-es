---
title: "Cadenas de formato de enumeración"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- format specifiers, enumeration format strings
- enumeration format strings
- formatting [.NET Framework], enumeration
ms.assetid: dd1ff672-1052-42cf-8666-4924fb6cd1a1
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 58004fa19f2ec3b1ca7570d6ca75702510148002
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="enumeration-format-strings"></a>Cadenas de formato de enumeración
Puede usar el método <xref:System.Enum.ToString%2A?displayProperty=nameWithType> para crear un objeto de cadena que represente el valor de cadena, numérico o hexadecimal del miembro de una enumeración. Este método toma una de las cadenas de formato de enumeración para especificar el valor que quiere que se devuelva.  
  
 En la tabla siguiente se enumeran las cadenas de formato de enumeración y los valores que devuelven. Estos especificadores de formato no distinguen mayúsculas de minúsculas.  
  
| Cadena de formato | Resultado |  
| ------------- | ------ |  
| G o g | Si es posible, muestra la entrada de enumeración como valor de cadena y, si no, muestra el valor entero de la instancia actual. Si la enumeración se define con el conjunto de atributos **Flags**, los valores de cadena de cada entrada válida se concatenan, separados por comas. Si no se establece el atributo **Flags**, se muestra un valor no válido como entrada numérica. En el siguiente ejemplo se muestra el uso del especificador de formato G.<br><br>[!code-csharp[Formatting.Enum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#1)] [!code-vb[Formatting.Enum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#1)] |  
| F o f | Si es posible, muestra la entrada de enumeración como valor de cadena. Si el valor se puede mostrar por completo como suma de las entradas de la enumeración (aunque el atributo **Flags** no esté presente), los valores de cadena de cada entrada válida se concatenan, separados por comas. Si las entradas de enumeración no pueden determinar completamente el valor, a este se le da formato como valor entero. En el siguiente ejemplo se muestra el uso del especificador de formato F.<br><br>[!code-csharp[Formatting.Enum#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#2)] [!code-vb[Formatting.Enum#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#2)] |  
| D o d | Muestra la entrada de enumeración como valor entero en la representación más corta posible. En el siguiente ejemplo se muestra el uso del especificador de formato D.<br><br>[!code-csharp[Formatting.Enum#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#3)] [!code-vb[Formatting.Enum#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#3)] |  
| X o x | Muestra la entrada de enumeración como valor hexadecimal. En caso necesario, el valor se representa con ceros iniciales para asegurarse de que tenga como mínimo ocho dígitos de longitud. En el siguiente ejemplo se muestra el uso del especificador de formato X.<br /><br /> [!code-csharp[Formatting.Enum#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#4)] [!code-vb[Formatting.Enum#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#4)] |  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define una enumeración denominada `Colors` que consta de tres entradas: `Red`, `Blue` y `Green`.  
  
 [!code-csharp[Formatting.Enum#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#5)]
 [!code-vb[Formatting.Enum#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#5)]  
  
 Una vez definida la enumeración, se puede declarar una instancia de la siguiente manera.  
  
 [!code-csharp[Formatting.Enum#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#6)]
 [!code-vb[Formatting.Enum#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#6)]  
  
 Luego se puede usar el método `Color.ToString(System.String)` para mostrar el valor de enumeración de maneras diferentes, según el especificador de formato pasado.  
  
 [!code-csharp[Formatting.Enum#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.Enum/cs/enum1.cs#7)]
 [!code-vb[Formatting.Enum#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.Enum/vb/enum1.vb#7)]  
  
## <a name="see-also"></a>Vea también  
 [Aplicación de formato a tipos](../../../docs/standard/base-types/formatting-types.md)
