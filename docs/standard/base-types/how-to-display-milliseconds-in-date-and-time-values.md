---
title: "C&#243;mo: Mostrar milisegundos en los valores de fecha y hora | Microsoft Docs"
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
  - "fechas [.NET Framework], milisegundos"
  - "DateTime.ToString (método)"
  - "mostrar datos de fecha y hora"
  - "milisegundos [.NET Framework]"
  - "hora [.NET Framework], milisegundos"
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Mostrar milisegundos en los valores de fecha y hora
Los métodos de formato de fecha y hora predeterminados, como <xref:System.DateTime.ToString?displayProperty=fullName>, incluyen las horas, minutos y segundos de un valor de tiempo, pero excluyen el componente correspondiente a los milisegundos.  En este tema se muestra cómo se incluye un componente de milisegundos de un valor de fecha y hora en cadenas de fecha y hora con formato.  
  
### Para mostrar el componente de milisegundos de un valor DateTime  
  
1.  Cuando trabaje con la representación de cadena de una fecha, conviértala en un valor <xref:System.DateTime> o <xref:System.DateTimeOffset> mediante el método estático <xref:System.DateTime.Parse%28System.String%29?displayProperty=fullName> o <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=fullName>.  
  
2.  Para extraer la representación de cadena del componente de milisegundos de una hora, llame al método <xref:System.DateTime.ToString%28System.String%29?displayProperty=fullName> o <xref:System.DateTimeOffset.ToString%2A> del valor de fecha y hora y pase el modelo de formato personalizado `fff` o `FFF` en solitario o junto a otros especificadores de formato personalizado como el parámetro `format`.  
  
## Ejemplo  
 En el ejemplo se muestra el componente de milisegundos de un valor <xref:System.DateTime> y <xref:System.DateTimeOffset> en la consola en su presentación en solitario e incluido en una cadena de fecha y hora más larga.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 El modelo de formato `fff` incluye todos los ceros finales en el valor de milisegundos.  El modelo de formato `FFF` suprime todos estos ceros.  En el siguiente ejemplo se ilustra la diferencia.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 Un problema que surge al definir un especificador de formato personalizado completo que incluya el componente de milisegundos de un valor de fecha y hora es que éste establece un formato codificado de forma rígida que es posible que no se corresponda con la organización de elementos horarios de la referencia cultural actual de la aplicación.  Una alternativa más conveniente consiste en recuperar uno de los modelos de presentación de fecha y hora definidos por el objeto <xref:System.Globalization.DateTimeFormatInfo> de la referencia cultural actual y modificarlo para incluir los milisegundos.  En el ejemplo se muestra también este enfoque.  En este ejemplo, se recupera el modelo completo de fecha y hora de la referencia cultural actual de la propiedad <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=fullName> y, a continuación, se inserta el modelo personalizado `.ffff` tras el segundo modelo.  Observe que en el ejemplo se utiliza una expresión regular para realizar esta operación en una única llamada al método.  
  
 También puede utilizar un especificador de formato personalizado para mostrar una fracción de segundo distinta de los milisegundos.  Por ejemplo, el especificador de formato personalizado `f` o `F` muestra las décimas de segundo, el especificador de formato personalizado `ff` o `FF` muestra las centésimas de segundo y el especificador de formato personalizado `ffff` o `FFFF` muestra las diezmilésimas de segundo.  Las fracciones de milisegundo se truncan en lugar de redondearse en la cadena devuelta.  Estos especificadores de formato se utilizan en el ejemplo siguiente.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  Es posible mostrar unidades fraccionarias de segundo muy pequeñas, como diezmilésimas o cienmilésimas de segundo.  Sin embargo, estos valores no suelen ser significativos.  La precisión de los valores de fecha y hora depende de la resolución del reloj del sistema.  En Windows NT 3.5 y versiones posteriores y en los sistemas operativos de [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], la resolución del reloj es aproximadamente 10\-15 milisegundos.  
  
## Compilar el código  
 Compile el código de la línea de comandos mediante csc.exe o vb.exe.  Para compilar el código de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Cadenas con formato de fecha y hora personalizado](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)