---
title: "Guardar y restaurar zonas horarias | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "deserialización [.NET Framework], zonas horarias"
  - "restaurar zonas horarias"
  - "guardar zonas horarias"
  - "serialización [ .NET Framework], zonas horarias"
  - "objetos de zonas horarias [.NET Framework], deserializar"
  - "objetos de zonas horarias [.NET Framework], restaurar"
  - "objetos de zonas horarias [.NET Framework], guardar"
  - "objetos de zonas horarias [.NET Framework], serializar"
  - "zonas horarias [.NET Framework], restaurar"
  - "zonas horarias [.NET Framework], guardar"
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Guardar y restaurar zonas horarias
La clase <xref:System.TimeZoneInfo> se basa en el Registro para recuperar información sobre la zona horaria predefinida.  Sin embargo, el Registro es una estructura dinámica.  Además, el sistema operativo utiliza la información sobre zonas horarias que el Registro contiene principalmente para realizar los ajustes de hora y las conversiones del año actual.  Esto tiene dos implicaciones importantes para las aplicaciones que se basan en información precisa sobre zonas horarias:  
  
-   Una zona horaria necesaria para una aplicación puede no estar definida en el Registro, o puede haber cambiado su nombre o haber sido quitada del Registro.  
  
-   Una zona horaria definida en el Registro puede carecer de información sobre reglas de ajuste determinadas necesarias para realizar conversiones de zonas horarias históricas.  
  
 La clase <xref:System.TimeZoneInfo> soluciona estas limitaciones porque admite la serialización \(guardar\) y deserialización \(restaurar\) de la información sobre zonas horarias.  
  
## Serialización y deserialización de zonas horarias  
 Guardar y restaurar una zona horaria mediante la serialización y deserialización de los datos de la misma implica dos llamadas a métodos:  
  
-   Puede serializar un objeto <xref:System.TimeZoneInfo> mediante una llamada al método <xref:System.TimeZoneInfo.ToSerializedString%2A> de ese objeto.  El método no toma ningún parámetro y devuelve una cadena que contiene información sobre la zona horaria.  
  
-   Puede deserializar un objeto <xref:System.TimeZoneInfo> de una cadena serializada pasando esa cadena al método <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=fullName> `static` \(`Shared` en Visual Basic\).  
  
## Casos de serialización y deserialización  
 La capacidad para guardar \(o serializar\) un objeto <xref:System.TimeZoneInfo> en una cadena y restaurarlo \(o deserializarlo\) para usarlo posteriormente aumenta la utilidad y la flexibilidad de la clase <xref:System.TimeZoneInfo>.  En esta sección se examinan algunas de las situaciones en que la serialización y la deserialización son muy útiles.  
  
### Serializar y deserializar datos de zonas horarias en una aplicación  
 Una zona horaria serializada se puede restaurar a partir de una cadena cuando se necesite.  Una aplicación puede hacerlo si la zona horaria recuperada del Registro no puede convertir correctamente una fecha y una hora dentro de un intervalo de fechas determinado.  Por ejemplo, los datos de zona horaria del Registro de Windows XP admiten una única regla de ajuste, mientras que las zonas horarias definidas en el Registro de Windows Vista proporcionan normalmente información sobre dos reglas de ajuste.  Esto significa que las conversiones horarias históricas pueden ser inexactas.  La serialización y deserialización de datos de zona horaria pueden tratar esta limitación.  
  
 En el ejemplo siguiente, una clase personalizada de <xref:System.TimeZoneInfo> que no tiene ninguna regla de ajuste se define para representar la zona horaria estándar de EE.UU. el este a partir de 1883 a 1917, antes de la introducción de horario de verano en Estados Unidos.  La zona horaria personalizada se serializa en una variable que tiene un ámbito global.  El método de conversión de zona horaria, `ConvertUtcTime`, recibe las horas UTC que se van a convertir.  Si la fecha y la hora son anteriores a 1917, la zona horaria estándar personalizada de la costa atlántica se restaura a partir de una cadena serializada y reemplaza la zona horaria recuperada del Registro.  
  
 [!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]  
  
### Tratar excepciones de zona horaria  
 Dado que el Registro es una estructura dinámica, su contenido está sujeto a modificaciones accidentales o intencionadas.  Esto significa que es posible que no se encuentre una zona horaria que debe estar definida en el Registro y que una aplicación necesita para ejecutarse correctamente.  Si no se admite la serialización y deserialización de las zonas horarias, solo tiene la opción de tratar la excepción <xref:System.TimeZoneNotFoundException> resultante finalizando la aplicación.  Sin embargo, con la serialización y deserialización de las zonas horarias, puede tratar una excepción <xref:System.TimeZoneNotFoundException> imprevista restaurando la zona horaria necesaria a partir de una cadena serializada, y la aplicación continuará ejecutándose.  
  
 En el ejemplo siguiente se crea y serializa una zona horaria estándar central personalizada.  Después, se intenta recuperar la zona horaria estándar central del Registro.  Si la operación de la recuperación produce una excepción <xref:System.TimeZoneNotFoundException> o <xref:System.InvalidTimeZoneException>, el controlador de excepciones deserializa la zona horaria.  
  
 [!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
 [!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]  
  
### Almacenar una cadena serializada y restaurarla cuando se necesita  
 En los ejemplos anteriores se ha almacenado información de la zona horaria en una variable de cadena y se ha restaurado cuando ha sido necesario.  Sin embargo, la cadena que contiene la información de la zona horaria serializada se puede almacenar en algunos medios de almacenamiento, como un archivo externo, un archivo de recursos incrustado en la aplicación, o el Registro. \(Tenga en cuenta que la información sobre las zonas horarias personalizadas se debe almacenar separada de las claves de zona horaria del sistema en el Registro\).  
  
 Al almacenar de esta manera la cadena de una zona horaria serializada, también se separa la rutina de creación de zonas horarias de la propia aplicación.  Por ejemplo, una rutina de creación de zonas horarias puede ejecutar y crear un archivo de datos que contiene información histórica de las zonas horarias que una aplicación puede utilizar.  El archivo de datos se puede instalar con la aplicación, se puede abrir, y una o varias de las zonas horarias se pueden deserializar cuando la aplicación las necesite.  
  
 Para obtener un ejemplo que utiliza un recurso incrustado para almacenar datos de zonas horarias serializadas, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)