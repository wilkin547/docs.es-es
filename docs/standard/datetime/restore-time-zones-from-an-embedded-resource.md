---
title: 'Cómo: restaurar zonas horarias de un recurso incrustado'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485777"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Cómo: restaurar zonas horarias de un recurso incrustado

Este tema describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos. Para obtener información e instrucciones acerca de cómo guardar zonas horarias, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Para deserializar un objeto TimeZoneInfo de un recurso incrustado

1. Si la zona horaria va a recuperar no es una zona horaria personalizada, intente crear instancias mediante la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.

2. Crear una instancia de un <xref:System.Resources.ResourceManager> pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.

   Si no se puede determinar el nombre completo del archivo de recursos incrustado, utilice la [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado. Un `.mresource` entrada identifica el recurso. En el ejemplo, es el nombre completo del recurso `SerializeTimeZoneData.SerializedTimeZones`.

   Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de la zona horaria, puede recuperar una referencia a él mediante una llamada a la `static` (`Shared` en Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> método.

3. Si la llamada a la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método se produce un error, o si es una zona horaria personalizada que se creará una instancia, recuperar una cadena que contiene la zona horaria serializada mediante una llamada a la <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> método.

4. Deserializar los datos de zona horaria mediante una llamada a la <xref:System.TimeZoneInfo.FromSerializedString%2A> método.

## <a name="example"></a>Ejemplo

El siguiente ejemplo se deserializa un <xref:System.TimeZoneInfo> objeto almacenado en un archivo de recursos de .NET XML incrustado.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Este código muestra el control de excepciones para asegurarse de que un <xref:System.TimeZoneInfo> objeto requerido por la aplicación está presente. Primero intenta crear una instancia de un <xref:System.TimeZoneInfo> objeto recuperarlos desde el registro mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método. Si no pueden crearse instancias de la zona horaria, el código recupera del archivo de recursos incrustado.

Porque datos para las zonas horarias personalizadas (zonas horarias que crea una instancia mediante el <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método) no se almacenan en el registro, el código no llama a la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para crear instancias de la zona horaria para Palmer, Antártida. En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes de llamar a la <xref:System.TimeZoneInfo.FromSerializedString%2A> método.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se agregarán al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.

* Que se importarán los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

* [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
* [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
* [Guardado de zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
