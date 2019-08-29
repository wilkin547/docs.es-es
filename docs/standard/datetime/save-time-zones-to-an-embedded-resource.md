---
title: Procedimiento para guardar zonas horarias en un recurso incrustado
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca39d989cc7bc16ec2678ba5fa53710899f3ac4
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107153"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Procedimiento para guardar zonas horarias en un recurso incrustado

Una aplicación que tiene en cuenta la zona horaria suele requerir la presencia de una zona horaria determinada. Sin embargo, dado que la disponibilidad <xref:System.TimeZoneInfo> de objetos individuales depende de la información almacenada en el registro del sistema local, es posible que las zonas horarias disponibles normalmente no estén presentes. Además, la información sobre las zonas horarias personalizadas de las que <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> se ha creado una instancia mediante el método no se almacena con otra información de zona horaria en el registro. Para asegurarse de que estas zonas horarias estén disponibles cuando se necesiten, puede guardarlas mediante su serialización y, posteriormente, restaurarlas mediante su deserialización.

Normalmente, la serialización <xref:System.TimeZoneInfo> de un objeto se produce aparte de la aplicación que tiene en cuenta la zona horaria. Dependiendo del almacén de datos utilizado para contener <xref:System.TimeZoneInfo> objetos serializados, los datos de zona horaria se pueden serializar como parte de una rutina de instalación o configuración (por ejemplo, cuando los datos se almacenan en una clave de aplicación del registro) o como parte de una rutina de utilidad que ejecuta antes de que se compile la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (. resx) de .NET XML).

Además de un archivo de recursos que se compila con la aplicación, se pueden usar otros almacenes de datos para la información de zona horaria. Entre ellas se incluyen las siguientes:

- El registro. Tenga en cuenta que una aplicación debe usar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizados en lugar de usar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

- Archivos de configuración.

- Otros archivos del sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Para guardar una zona horaria mediante su serialización en un archivo. resx

1. Recuperar una zona horaria existente o crear una nueva zona horaria.

   Para recuperar una zona horaria existente, consulte [cómo: Obtener acceso a los objetos](../../../docs/standard/datetime/access-utc-and-local.md) de zona horaria local y UTC predefinidos y [cómo: Cree una instancia de un](../../../docs/standard/datetime/instantiate-time-zone-info.md)objeto TimeZoneInfo.

   Para crear una nueva zona horaria, llame a una de las sobrecargas del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método. Para obtener más información, consulte [Cómo Cree zonas horarias sin reglas](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) de [ajuste y cómo: Cree zonas horarias con reglas](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)de ajuste.

2. Llame al <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contenga los datos de la zona horaria.

3. Cree una instancia <xref:System.IO.StreamWriter> de un objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo <xref:System.IO.StreamWriter> . resx al constructor de clase.

4. Cree una instancia <xref:System.Resources.ResXResourceWriter> de un objeto pasando <xref:System.IO.StreamWriter> el objeto al <xref:System.Resources.ResXResourceWriter> constructor de clase.

5. Pase la cadena serializada de la zona horaria al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.

6. Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Cierre el <xref:System.IO.StreamWriter> objeto llamando a su <xref:System.IO.StreamWriter.Close%2A> método.

9. Agregue el archivo. resx generado al proyecto de Visual Studio de la aplicación.

10. Con la ventana **propiedades** de Visual Studio, asegúrese de que la propiedad **acción de compilación** del archivo. resx esté establecida en **recurso incrustado**.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo, se <xref:System.TimeZoneInfo> serializa un objeto que representa la hora estándar <xref:System.TimeZoneInfo> central y un objeto que representa el tiempo de la estación Palmer, en un archivo de recursos XML de .net denominado SerializedTimeZones. resx. Normalmente, la hora estándar central se define en el registro; La estación de Palmer, la Antártida es una zona horaria personalizada.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

En este ejemplo se <xref:System.TimeZoneInfo> serializan objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.

Dado que <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> el método agrega información de encabezado completa a un archivo de recursos de .net XML, no se puede usar para agregar recursos a un archivo existente. Para controlar esto, el ejemplo se comprueba para el archivo SerializedTimeZones. resx y, si existe, se almacenan todos sus recursos distintos de las dos zonas horarias serializadas <xref:System.Collections.Generic.Dictionary%602> en un objeto genérico. A continuación, se elimina el archivo existente y se agregan los recursos existentes a un nuevo archivo SerializedTimeZones. resx. Los datos de zona horaria serializados también se agregan a este archivo.

Los campos de clave (o **nombre**) de los recursos no deben contener espacios incrustados. Se llama al método para quitar todos los espacios incrustados de los identificadores de zona horaria antes de que se asignen al archivo de recursos. <xref:System.String.Replace%28System.String%2CSystem.String%29>

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Procedimientos: Restauración de zonas horarias desde un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
