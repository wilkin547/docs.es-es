---
title: "C&#243;mo: Guardar zonas horarias en un recurso incrustado | Microsoft Docs"
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
  - "objetos de zonas horarias [.NET Framework], guardar"
  - "objetos de zonas horarias [.NET Framework], serializar"
  - "zonas horarias [.NET Framework], guardar"
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Guardar zonas horarias en un recurso incrustado
Una aplicación que tiene en cuenta la zona horaria requiere a menudo la presencia de una zona horaria determinada.  Sin embargo, como la disponibilidad de objetos <xref:System.TimeZoneInfo> individuales depende de la información almacenada en el Registro del sistema local, puede suceder que incluso las zonas horarias personalizadas no se encuentren.  Además, la información sobre zonas horarias personalizadas cuya instancia se creó utilizando el método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> no se almacena con otra información sobre zonas horarias en el Registro.  Para garantizar que estas zonas horarias estén disponibles cuando se necesiten, puede serializarlas para guardarlas y, después, deserializarlas para restaurarlas.  
  
 Normalmente, la serialización de un objeto <xref:System.TimeZoneInfo> se realiza de forma separada de la aplicación que tiene en cuenta la zona horaria.  Dependiendo del almacén de datos utilizado para contener los objetos <xref:System.TimeZoneInfo> serializados, los datos de zona horaria se pueden serializar como parte de una instalación o rutina de instalación \(por ejemplo, cuando los datos se almacenan en una clave de aplicación del Registro\) o como parte de una rutina de utilidad que se ejecuta antes de que la última aplicación esté compilada \(por ejemplo, cuando los datos serializados se almacenan en un archivo de recurso XML \(.resx\) de .NET\).  
  
 Además de un archivo de recursos compilado con la aplicación, se pueden usar otros almacenes de datos para información sobre zonas horarias.  Entre ellos, se incluyen los siguientes:  
  
-   El Registro.  Tenga en cuenta que una aplicación debe utilizar las subclaves de su propia clave de aplicación para almacenar los datos de zonas horarias personalizados en lugar de utilizar las subclaves de HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Time Zones.  
  
-   Archivos de configuración.  
  
-   Otros archivos de sistema.  
  
### Para guardar una zona horaria serializándola en un archivo .resx  
  
1.  Recupere una zona horaria existente o cree una zona horaria nueva.  
  
     Para recuperar una zona horaria existente, vea [Cómo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md) y [Cómo: Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).  
  
     Para crear una zona horaria nueva, llame a una de las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  Para obtener más información, vea [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
  
2.  Llame al método <xref:System.TimeZoneInfo.ToSerializedString%2A> para crear una cadena que contenga los datos de la zona horaria.  
  
3.  Cree instancias de un objeto <xref:System.IO.StreamWriter> proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo .resx al constructor de la clase <xref:System.IO.StreamWriter>.  
  
4.  Cree instancias de un objeto <xref:System.Resources.ResXResourceWriter> pasando el objeto <xref:System.IO.StreamWriter> al constructor de la clase <xref:System.Resources.ResXResourceWriter>.  
  
5.  Pase la cadena serializada de la zona horaria al método <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=fullName>.  
  
6.  Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName>.  
  
7.  Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=fullName>.  
  
8.  Cierre el objeto <xref:System.IO.StreamWriter> llamando a su método <xref:System.IO.StreamWriter.Close%2A>.  
  
9. Agregue el archivo .resx generado al proyecto de Visual Studio de la aplicación.  
  
10. Utilice la ventana **Propiedades** de Visual Studio para asegurarse de que la propiedad **Acción de compilación** del archivo .resx está establecida en **Recurso incrustado**.  
  
## Ejemplo  
 En el ejemplo siguiente se serializan un objeto <xref:System.TimeZoneInfo> que representa la hora estándar central y un objeto <xref:System.TimeZoneInfo> que representa la hora de la Base Palmer, en la Antártida, a un archivo de recursos XML de .NET denominado SerializedTimeZones.resx.  Normalmente, la hora estándar central está definida en el Registro; la Base Palmer, en la Antártida, es una zona horaria personalizada.  
  
 [!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
 [!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]  
  
 En este ejemplo se serializan objetos <xref:System.TimeZoneInfo> para que estén disponibles en un archivo de recursos en tiempo de compilación.  
  
 Debido a que el método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=fullName> agrega la información de encabezado completa a un archivo de recursos XML de .NET, no se puede utilizar para agregar recursos a un archivo existente.  En el ejemplo, esto se trata buscando el archivo SerializedTimeZones.resx y, si existe, almacenando todos los recursos que no sean las dos zonas horarias serializadas en un objeto <xref:System.Collections.Generic.Dictionary%602> genérico.  Después, se elimina el archivo existente y los recursos existentes se agregan a un nuevo archivo SerializedTimeZones.resx.  Los datos de zona horaria serializada también se agregan a este archivo.  
  
 Los campos clave \(o **Nombre**\) de los recursos no deben contener espacios incrustados.  Se llama al método <xref:System.String.Replace%28System.String%2CSystem.String%29> para quitar todos los espacios incrustados en los identificadores de zona horaria antes de asignarlos al archivo de recursos.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.  
  
-   Que se importen los siguientes espacios de nombres:  
  
     [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
     [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)   
 [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)