---
title: "dateTimeInvalidLocalFormat MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "dates [.NET Framework], formatting"
  - "invalid date time local format"
  - "invalid local formats"
  - "MDAs (managed debugging assistants), invalid local formats"
  - "managed debugging assistants (MDAs), invalid local formats"
  - "dateTimeInvalidLocalFormat MDA"
  - "date formatting"
  - "time formatting"
  - "UTC formatting"
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# dateTimeInvalidLocalFormat MDA
El MDA `dateTimeInvalidLocalFormat` se activa cuando una instancia de <xref:System.DateTime> que está almacenada como hora universal coordinada \(UTC\) tiene un formato pensado para su uso exclusivo para instancias de <xref:System.DateTime> locales.  Este MDA no se activa para las instancias de <xref:System.DateTime> no especificadas o predeterminadas.  
  
## Síntoma  
 Una aplicación está serializando manualmente una instancia de <xref:System.DateTime> UTC utilizando un formato local:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### Motivo  
 El formato de 'z' para el método <xref:System.DateTime.ToString%2A?displayProperty=fullName> incluye el desplazamiento de zona de hora local, por ejemplo, "\+10:00" para la hora de Sydney.  Como tal, sólo generará un resultado significativo si el valor de <xref:System.DateTime> es local.  Si el valor es la hora UTC, <xref:System.DateTime.ToString%2A?displayProperty=fullName> incluye el desplazamiento de zona de hora local, pero no muestra ni ajusta el especificador de la zona horaria.  
  
### Resolución  
 Las instancias de <xref:System.DateTime> UTC deberían tener un formato que indique que son del tipo UTC.  Formato recomendado para las horas UTC que utilizan un valor de 'Z' para indicar la hora UTC:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 También hay un formato "o" que serializa un <xref:System.DateTime> utilizando la propiedad <xref:System.DateTime.Kind%2A> que serializa correctamente independientemente de si la instancia es local, UTC o no está especificada:  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## Efecto en el Runtime  
 Este MDA no afecta al tiempo de ejecución.  
  
## Resultados  
 La activación de MDA no produce ningún resultado especial. Sin embargo, la pila de llamadas se puede utilizar para averiguar la ubicación de la llamada <xref:System.DateTime.ToString%2A> que activó el MDA.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## Ejemplo  
 Considere una aplicación que está serializando indirectamente un valor de <xref:System.DateTime> UTC utilizando la clase <xref:System.Xml.XmlConvert> o <xref:System.Data.DataSet>, de la siguiente manera.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 Las serializaciones <xref:System.Xml.XmlConvert> y <xref:System.Data.DataSet> utilizan de forma predeterminada los formatos locales para la serialización.  Para serializar otros tipos de valores de <xref:System.DateTime>, como UTC, se requieren opciones adicionales.  
  
 Para obtener este ejemplo concreto, pase `XmlDateTimeSerializationMode.RoundtripKind` a la llamada `ToString` de `XmlConvert`.  Así se serializan los datos como una hora UTC.  
  
 Si se está utilizando un <xref:System.Data.DataSet>, establezca la propiedad <xref:System.Data.DataColumn.DateTimeMode%2A> del objeto <xref:System.Data.DataColumn> en <xref:System.Data.DataSetDateTime>.  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## Vea también  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)