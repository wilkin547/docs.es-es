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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 921874e774d18751c29db495dac1bc53d10cc8ad
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211858"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>Cómo: guardar zonas horarias en un recurso incrustado

Una aplicación compatible con zona horaria a menudo requiere la presencia de una zona horaria determinada. Sin embargo, dado que la disponibilidad de la persona <xref:System.TimeZoneInfo> objetos depende de la información almacenada en el registro del sistema local, las zonas horarias disponibles habitualmente incluso puede que falte. Además, crea una instancia de información sobre zonas horarias personalizadas mediante el uso de la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se almacena con otra información de zona horaria en el registro. Para asegurarse de que estas zonas horarias están disponibles cuando se necesiten, puede serializarlas para ellos y restaurarlas más adelante mediante la deserialización de ellos.

Normalmente, serializar un <xref:System.TimeZoneInfo> objeto aparece además de las aplicaciones basadas en la zona horaria. Según el almacén de datos que se usa para contener serializada <xref:System.TimeZoneInfo> objetos, datos de zona horaria se pueden serializar como parte de una rutina de configuración o instalación (por ejemplo, cuando los datos se almacenan en una clave del registro de aplicación), o como parte de una rutina de la utilidad que se ejecuta antes de que se compila la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (.resx) XML. NET).

Un archivo de recursos que se compila con la aplicación, además de otros almacenes de datos pueden utilizarse para obtener información de zona horaria. Entre ellas se incluyen las siguientes:

* El registro. Tenga en cuenta que una aplicación debe utilizar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizada en lugar de utilizar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.

* Archivos de configuración.

* Otros archivos del sistema.

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>Para guardar una zona horaria serializándolo en un archivo .resx

1. Recuperar una zona horaria existente o crear una nueva zona horaria.

   Para recuperar una zona horaria existente, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md) y [Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).

   Para crear una nueva zona horaria, llame a una de las sobrecargas de los <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método. Para obtener más información, consulte [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).

2. Llame a la <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contiene los datos de la zona horaria.

3. Crear una instancia de un <xref:System.IO.StreamWriter> objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo .resx que el <xref:System.IO.StreamWriter> constructor de clase.

4. Crear una instancia de un <xref:System.Resources.ResXResourceWriter> pasando el <xref:System.IO.StreamWriter> de objeto para el <xref:System.Resources.ResXResourceWriter> constructor de clase.

5. Pase la zona horaria serializa la cadena para el <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.

6. Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.

7. Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.

8. Cerrar la <xref:System.IO.StreamWriter> objeto mediante una llamada a su <xref:System.IO.StreamWriter.Close%2A> método.

9. Agregue el archivo .resx generado al proyecto de Visual Studio de la aplicación.

10. Mediante el **propiedades** ventana en Visual Studio, asegúrese de que el archivo .resx **acción de compilación** propiedad está establecida en **recurso incrustado**.

## <a name="example"></a>Ejemplo

El ejemplo siguiente se serializa un <xref:System.TimeZoneInfo> objeto que representa la hora estándar Central y un <xref:System.TimeZoneInfo> objeto que representa la Estación Palmer, la hora de Antártida en un archivo de recursos XML de .NET que se denomina SerializedTimeZones.resx. Hora estándar central normalmente se define en el registro; Estación Palmer, Antártida es una zona horaria personalizada.

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

En este ejemplo, se serializa <xref:System.TimeZoneInfo> objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.

Dado que el <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> método agrega información de encabezado completa a un archivo de recursos XML de .NET, no se puede usar para agregar recursos a un archivo existente. El ejemplo controla mediante la comprobación del archivo SerializedTimeZones.resx y, si existe, almacenar todos sus recursos distintos de las dos zonas horarias serializan en un tipo genérico <xref:System.Collections.Generic.Dictionary%602> objeto. A continuación, se elimina el archivo existente y los recursos existentes se agregan a un nuevo archivo SerializedTimeZones.resx. Los datos de zona horaria serializada también se agregan a este archivo.

La clave (o **nombre**) los campos de recursos no deben contener espacios incrustados. El <xref:System.String.Replace%28System.String%2CSystem.String%29> método se llama para quitar todos los espacios insertados en los identificadores de zona horaria antes de que están asignadas al archivo de recursos.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
* [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
* [Restauración de zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
