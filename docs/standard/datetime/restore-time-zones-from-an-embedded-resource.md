---
title: "C&#243;mo: Restaurar zonas horarias de un recurso incrustado | Microsoft Docs"
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
  - "zonas horarias [.NET Framework], deserializar"
  - "zonas horarias [.NET Framework], restaurar"
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Restaurar zonas horarias de un recurso incrustado
En este tema se describe cómo restaurar las zonas horarias guardadas en un archivo de recursos.  Para obtener información e instrucciones sobre cómo guardar zonas horarias, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).  
  
### Para deserializar un objeto TimeZoneInfo a partir de un recurso incrustado  
  
1.  Si la zona horaria que se va a recuperar no es una zona horaria personalizada, intente crear instancias de ella con el método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.  
  
2.  Cree instancias de un objeto <xref:System.Resources.ResourceManager> pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.  
  
     Si no puede determinar el nombre completo del archivo de recursos incrustado, utilice [Ildasm.exe \(IL Disassembler\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado.  Una entrada `.mresource` identifica el recurso.  En el ejemplo, el nombre completo del recurso es `SerializeTimeZoneData.SerializedTimeZones`.  
  
     Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de la zona horaria, puede recuperar una referencia a él llamando al método `static`, \(`Shared` en Visual Basic\) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A>.  
  
3.  Si se produce un error en la llamada al método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>, o si hay que crear instancias de una zona horaria personalizada, recupere una cadena que contenga la zona horaria serializada llamando al método <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=fullName>.  
  
4.  Deserialice los datos de la zona horaria llamando al método <xref:System.TimeZoneInfo.FromSerializedString%2A>.  
  
## Ejemplo  
 En el ejemplo siguiente se deserializa un objeto <xref:System.TimeZoneInfo> almacenado en un archivo de recursos XML de .NET incrustado.  
  
 [!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
 [!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]  
  
 Este código muestra el control de excepciones para garantizar que un objeto <xref:System.TimeZoneInfo> requerido por la aplicación está presente.  En primer lugar, intenta crear instancias de un objeto <xref:System.TimeZoneInfo> recuperándolo del Registro mediante el método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.  Si no se puede crear una instancia de la zona horaria, el código lo recupera del archivo de recursos incrustado.  
  
 Debido a que los datos de las zonas horarias personalizadas \(zonas horarias de las que se crearon instancias utilizando el método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>\) no se almacenan en el Registro, el código no llama al método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para crear las instancias de la zona horaria de Base Palmer, en la Antártida.  En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contenga los datos de la zona horaria antes de llamar al método <xref:System.TimeZoneInfo.FromSerializedString%2A>.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.  
  
-   Que se importen los siguientes espacios de nombres:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)   
 [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)