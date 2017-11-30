---
title: "Conversión de tipos de datos XML"
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
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a>Conversión de tipos de datos XML
La mayoría de los métodos que se encuentra en un **XmlConvert** clase se utilizan para convertir datos entre cadenas y formatos fuertemente tipados. Los métodos son independientes de la configuración regional. Esto significa que no la tienen en cuenta al realizar la conversión.  
  
## <a name="reading-string-as-types"></a>Leer cadenas como tipos  
 El ejemplo siguiente se lee una cadena y se convierte en una **DateTime** tipo.  
  
 Dada la siguiente entrada XML:  
  
 **Entrada**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 Este código convierte la cadena a la **DateTime** formato:  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a>Escribir cadenas como tipos  
 El siguiente ejemplo se lee un **Int32** y lo convierte en una cadena.  
  
 Dada la siguiente entrada XML:  
  
 **Entrada**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 Este código convierte el **Int32** en un **cadena**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>Vea también  
 [Convertir cadenas en tipos de datos de .NET Framework](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [Convertir tipos de .NET Framework en cadenas](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
