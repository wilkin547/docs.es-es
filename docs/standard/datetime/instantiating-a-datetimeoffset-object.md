---
title: "Crear instancias de un objeto DateTimeOffset | Microsoft Docs"
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
  - "crear instancias de objetos de zonas horarias"
  - "objetos de zona horaria [.NET Framework], creación de instancias"
  - "DateTimeOffset (estructura), convertir a DateTime"
  - "DateTimeOffset (estructura), crear instancias"
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Crear instancias de un objeto DateTimeOffset
La estructura de <xref:System.DateTimeOffset> proporciona varias maneras de crear nuevos valores de <xref:System.DateTimeOffset> .  Muchos de ellos corresponden directamente a los métodos disponibles para crear instancias de los nuevos valores de <xref:System.DateTime>, con mejoras que permiten especificar la fecha y la diferencia horaria respecto a la hora universal coordinada \(UTC\).  En particular, puede crear instancias de un valor <xref:System.DateTimeOffset> de las siguientes maneras:  
  
-   Utilizando un literal de fecha y hora.  
  
-   Llamando a un constructor <xref:System.DateTimeOffset>.  
  
-   Convirtiendo implícitamente un valor en un valor <xref:System.DateTimeOffset>.  
  
-   Analizando la representación de cadena de una fecha y hora.  
  
 En este tema se ofrece información más detallada y ejemplos de código que muestran estos métodos para crear instancias de los nuevos valores de <xref:System.DateTimeOffset>.  
  
## Literales de fecha y hora  
 Para los lenguajes que lo admiten, una de las maneras más comunes de crear instancias de un valor <xref:System.DateTime> es proporcionar la fecha y hora como valor literal incluido en el código.  Por ejemplo, el siguiente código de Visual Basic crea un objeto <xref:System.DateTime> cuyo valor es el 1 de enero de 2008, 10:00 a.m.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]  
  
 Los valores de <xref:System.DateTimeOffset> también se pueden inicializar utilizando literales de fecha y hora cuando se utilizan lenguajes que admiten literales <xref:System.DateTime>.  Por ejemplo, el siguiente código de Visual Basic crea un objeto <xref:System.DateTimeOffset>.  
  
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]  
  
 Como muestra el resultado de la consola, se ha asignado la diferencia horaria de la zona horaria local al valor <xref:System.DateTimeOffset> creado de esta manera.  Esto significa que un valor <xref:System.DateTimeOffset> asignado mediante un literal de caracteres no identifica un punto único de tiempo si el código se ejecuta en equipos diferentes.  
  
## Constructores DateTimeOffset  
 El tipo <xref:System.DateTimeOffset> define seis constructores.  Cuatro de ellos corresponden directamente a los constructores <xref:System.DateTime>, con un parámetro adicional del tipo <xref:System.TimeSpan> que define la diferencia de hora y fecha respecto a UTC.  Éstos permiten definir un valor <xref:System.DateTimeOffset> basado en el valor de sus componentes de fecha y hora individuales.  Por ejemplo, el código siguiente utiliza estos cuatro constructores para crear instancias de los objetos <xref:System.DateTimeOffset> con los valores idénticos 7\/1\/2008 12:05 a.m. \+01:00.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]  
  
 Tenga en cuenta que, cuando se muestra en la consola el valor del objeto <xref:System.DateTimeOffset> cuya instancia se creó utilizando un objeto <xref:System.Globalization.PersianCalendar> como uno de los argumentos de su constructor, se expresa como una fecha del calendario gregoriano en lugar del calendario persa.  Para generar una fecha usando el calendario persa, vea el ejemplo en el tema <xref:System.Globalization.PersianCalendar>.  
  
 Los otros dos constructores crean un objeto <xref:System.DateTimeOffset> a partir de un valor <xref:System.DateTime>.  El primero tiene un único parámetro, el valor <xref:System.DateTime> que se va a convertir en un valor <xref:System.DateTimeOffset>.  La diferencia horaria del valor <xref:System.DateTimeOffset> resultante depende de la propiedad <xref:System.DateTime.Kind%2A> del único parámetro del constructor.  Si su valor es <xref:System.DateTimeKind?displayProperty=fullName>, la diferencia horaria es igual a <xref:System.TimeSpan.Zero?displayProperty=fullName>.  De lo contrario, la diferencia horaria será la de la zona horaria local.  El ejemplo siguiente muestra el uso de este constructor para crear instancias de los objetos <xref:System.DateTimeOffset> que representan la hora UTC y la zona horaria local:  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]  
  
> [!NOTE]
>  Llamar a la sobrecarga del constructor <xref:System.DateTimeOffset> que tiene un único parámetro <xref:System.DateTime> equivale a realizar una conversión implícita de un valor <xref:System.DateTime> en un valor <xref:System.DateTimeOffset>.  
  
 El segundo constructor que crea un objeto <xref:System.DateTimeOffset> a partir de un valor <xref:System.DateTime> tiene dos parámetros: el valor <xref:System.DateTime> que se va a convertir y un valor <xref:System.TimeSpan> que representa la diferencia de fecha y hora respecto a la hora UTC.  El valor de esta diferencia debe corresponder a la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro del constructor o se iniciará una <xref:System.ArgumentException>.  Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind?displayProperty=fullName>, el valor del segundo parámetro debe ser <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind?displayProperty=fullName>, el valor del segundo parámetro debe ser la diferencia horaria de la zona horaria del sistema local.  Si la propiedad <xref:System.DateTime.Kind%2A> del primer parámetro es <xref:System.DateTimeKind?displayProperty=fullName>, la diferencia horaria puede ser cualquier valor válido.  El código siguiente muestra las llamadas a este constructor para convertir <xref:System.DateTime> en valores <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]  
  
## Conversión de tipos implícita  
 El tipo <xref:System.DateTimeOffset> admite una conversión de tipos implícita: de un valor <xref:System.DateTime> a un valor <xref:System.DateTimeOffset>. \(Una conversión de tipos implícita es una conversión de un tipo a otro que no requiere una conversión de tipos explícita \(en C\# o Visual Basic\) y que no pierde información.  Hace que sea posible utilizar código como el siguiente.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]  
  
 La diferencia horaria del valor <xref:System.DateTimeOffset> resultante depende del valor de propiedad <xref:System.DateTime.Kind%2A?displayProperty=fullName>.  Si su valor es <xref:System.DateTimeKind?displayProperty=fullName>, la diferencia horaria es igual a <xref:System.TimeSpan.Zero?displayProperty=fullName>.  Si su valor es <xref:System.DateTimeKind?displayProperty=fullName> o <xref:System.DateTimeKind?displayProperty=fullName>, la diferencia horaria será la de la zona horaria local.  
  
## Analizar la representación de cadena de una fecha y hora  
 El tipo <xref:System.DateTimeOffset> admite cuatro métodos que permiten convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset>:  
  
-   <xref:System.DateTimeOffset.Parse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset> e inicia una excepción si se produce un error en la conversión.  
  
-   <xref:System.DateTimeOffset.TryParse%2A>, que intenta convertir la representación de cadena de una fecha y hora en un valor <xref:System.DateTimeOffset> y devuelve `false` si se produce un error en la conversión.  
  
-   <xref:System.DateTimeOffset.ParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora con un formato especificado en un valor <xref:System.DateTimeOffset>.  El método inicia excepción si se produce un error de conversión.  
  
-   <xref:System.DateTimeOffset.TryParseExact%2A>, que intenta convertir la representación de cadena de una fecha y hora con un formato especificado en un valor <xref:System.DateTimeOffset>.  El método devuelve `false` si se produce un error de conversión.  
  
 El ejemplo siguiente muestra llamadas a cada uno de estos cuatro métodos de conversión de cadenas para crear instancias de un valor <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)