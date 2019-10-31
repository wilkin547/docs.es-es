---
title: 'Cómo: guardar zonas horarias en un recurso incrustado'
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
ms.openlocfilehash: aaee4e82d09e8b604d06dadb5a5eefe8d2e1f307
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123767"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Cómo: guardar zonas horarias en un recurso incrustado

Una aplicación que tiene en cuenta la zona horaria suele requerir la presencia de una zona horaria determinada. Sin embargo, dado que la disponibilidad de los objetos individuales de <xref:System.TimeZoneInfo> depende de la información almacenada en el registro del sistema local, es posible que no existan las zonas horarias disponibles habitualmente. Además, la información sobre las zonas horarias personalizadas de las que se ha creado una instancia mediante el método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> no se almacena con otra información de zona horaria en el registro. Para asegurarse de que estas zonas horarias estén disponibles cuando se necesiten, puede guardarlas mediante su serialización y, posteriormente, restaurarlas mediante su deserialización.

Normalmente, la serialización de un objeto de <xref:System.TimeZoneInfo> se produce aparte de la aplicación que tiene en cuenta la zona horaria. En función del almacén de datos utilizado para almacenar objetos de <xref:System.TimeZoneInfo> serializados, los datos de zona horaria se pueden serializar como parte de una rutina de instalación o configuración (por ejemplo, cuando los datos se almacenan en una clave de aplicación del registro) o como parte de una rutina de utilidad que se ejecuta antes de la aplicación final se compila (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (. resx) de .NET XML).

Además de un archivo de recursos que se compila con la aplicación, se pueden usar otros almacenes de datos para la información de zona horaria. Entre ellas se incluyen las siguientes:

- El registro. Tenga en cuenta que una aplicación debe usar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizados en lugar de usar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

- Archivos de configuración.

- Otros archivos del sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Para guardar una zona horaria mediante su serialización en un archivo. resx

1. Recuperar una zona horaria existente o crear una nueva zona horaria.

   Para recuperar una zona horaria existente, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md) y [Cómo: crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Para crear una nueva zona horaria, llame a una de las sobrecargas del método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>. Para obtener más información, consulte [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Llame al método <xref:System.TimeZoneInfo.ToSerializedString%2A> para crear una cadena que contenga los datos de la zona horaria.

3. Cree una instancia de un objeto <xref:System.IO.StreamWriter> proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo. resx al constructor de la clase <xref:System.IO.StreamWriter>.

4. Cree una instancia de un objeto <xref:System.Resources.ResXResourceWriter> pasando el objeto <xref:System.IO.StreamWriter> al constructor de clase <xref:System.Resources.ResXResourceWriter>.

5. Pase la cadena serializada de la zona horaria al método <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType>.

6. Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Cierre el objeto <xref:System.IO.StreamWriter> llamando a su método <xref:System.IO.StreamWriter.Close%2A>.

9. Agregue el archivo. resx generado al proyecto de Visual Studio de la aplicación.

10. Con la ventana **propiedades** de Visual Studio, asegúrese de que la propiedad **acción de compilación** del archivo. resx esté establecida en **recurso incrustado**.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se serializa un objeto de <xref:System.TimeZoneInfo> que representa la hora estándar central y un objeto <xref:System.TimeZoneInfo> que representa el tiempo de la estación de Palmer, en un archivo de recursos XML de .NET denominado SerializedTimeZones. resx. Normalmente, la hora estándar central se define en el registro; La estación de Palmer, la Antártida es una zona horaria personalizada.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

En este ejemplo se serializan <xref:System.TimeZoneInfo> objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.

Dado que el método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> agrega información de encabezado completa a un archivo de recursos XML de .NET, no se puede usar para agregar recursos a un archivo existente. En el ejemplo se controla esto comprobando el archivo SerializedTimeZones. resx y, si existe, almacenando todos sus recursos distintos de las dos zonas horarias serializadas en un objeto de <xref:System.Collections.Generic.Dictionary%602> genérico. A continuación, se elimina el archivo existente y se agregan los recursos existentes a un nuevo archivo SerializedTimeZones. resx. Los datos de zona horaria serializados también se agregan a este archivo.

Los campos de clave (o **nombre**) de los recursos no deben contener espacios incrustados. Se llama al método <xref:System.String.Replace%28System.String%2CSystem.String%29> para quitar todos los espacios incrustados de los identificadores de zona horaria antes de que se asignen al archivo de recursos.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Restauración de zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
