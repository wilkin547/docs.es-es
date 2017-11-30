---
title: Convertir cadenas en tipos de datos de .NET Framework
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>Convertir cadenas en tipos de datos de .NET Framework
Si desea convertir una cadena en un tipo de datos de .NET Framework, use la **XmlConvert** método que se adapte a los requisitos de aplicación. Para obtener una lista de todos los métodos de conversión disponibles en la **XmlConvert** de clases, consulte <xref:System.Xml.XmlConvert>.  
  
 La cadena devuelta de la **ToString** método es una versión de cadena de los datos que se pasan. Además, hay varios tipos de .NET Framework que realizan la conversión mediante la **XmlConvert** clase, pero no utilizan los métodos de la **System.Convert** clase. El **XmlConvert** clase sigue la especificación de tipo de datos de esquemas XML (XSD) y tienen un tipo que el **XmlConvert** puede asignar a.  
  
 En la tabla siguiente se enumeran los tipos de datos de .NET Framework y los tipos de cadena que se devuelven mediante la asignación de tipos de datos de los esquemas XML (XSD). No se puede procesar estos tipos de .NET Framework mediante **System.Convert**.  
  
|Tipo de .NET Framework|Cadena devuelta|  
|-------------------------|---------------------|  
|Boolean|"true", "false"|  
|Single.PositiveInfinity|"INF"|  
|Single.NegativeInfinity|"-INF"|  
|Double.PositiveInfinity|"INF"|  
|Double.NegativeInfinity|"-INF"|  
|DateTime|El formato es "aaaa-MM-ddTHH:mm:sszzzzzz" y sus subconjuntos.|  
|Timespan|El formato es PnYnMnTnHnMnS, es decir, `P2Y10M15DT10H30M20S` corresponde a una duración de 2 años, 10 meses, 15 días, 10 horas, 30 minutos y 20 segundos.|  
  
> [!NOTE]
>  Si se convierte uno de los tipos de .NET Framework enumerados en la tabla en una cadena mediante el **ToString** método, la cadena devuelta no es el tipo base, pero el tipo de cadena de esquema XML (XSD).  
  
 El **DateTime** y **Timespan** difiere del tipo de valor en el que un **DateTime** representa un instante de tiempo, mientras que un **TimeSpan** Representa un intervalo de tiempo. El **DateTime** y **Timespan** formatos se especifican en la especificación de tipos de datos de esquemas XML (XSD). Por ejemplo:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **Salida**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 En el código siguiente se convierte un número entero en una cadena:  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **Salida**  
  
 `<Number>200</Number>`  
  
 Sin embargo, si va a convertir una cadena a **booleano**, **único**, o **doble**, el tipo de .NET Framework que se devuelve no es el mismo que el tipo devuelto al utilizar la **System.Convert** clase.  
  
## <a name="string-to-boolean"></a>Conversión de cadenas en Boolean  
 En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en **booleano** mediante la **ToBoolean** método.  
  
|Parámetro de entrada de cadena válido|Tipo de salida de .NET Framework|  
|----------------------------------|--------------------------------|  
|"true"|Boolean.True|  
|"1"|Boolean.True|  
|"false"|Boolean.False|  
|"0"|Boolean.False|  
  
 Por ejemplo, dado el siguiente código XML:  
  
 **Entrada**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 El código siguiente pueden entender ambas y **bvalue** es **System.Boolean.True**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>Conversión de cadenas en Single  
 En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en un **único** mediante la **ToSingle** método.  
  
|Parámetro de entrada de cadena válido|Tipo de salida de .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Single.PositiveInfinity|  
|"-INF"|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>Conversión de cadenas en Double  
 En la tabla siguiente se muestra qué tipo se genera para las cadenas de entrada dadas, al convertir una cadena en un **único** mediante la **ToDouble** método.  
  
|Parámetro de entrada de cadena válido|Tipo de salida de .NET Framework|  
|----------------------------------|--------------------------------|  
|"INF"|Double.PositiveInfinity|  
|"-INF"|Double.NegativeInfinity|  
  
 El código siguiente escribe `<Infinity>INF</Infinity>`:  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>Vea también  
 [Conversión de tipos de datos XML](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [Convertir tipos de .NET Framework en cadenas](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
