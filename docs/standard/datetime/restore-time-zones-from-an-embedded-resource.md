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
ms.openlocfilehash: cd2119d6d22f3f676b7167ed545aeb058123cfb5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122200"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Cómo: restaurar zonas horarias de un recurso incrustado

En este tema se describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos. Para obtener información e instrucciones sobre cómo guardar zonas horarias, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Para deserializar un objeto TimeZoneInfo desde un recurso incrustado

1. Si la zona horaria que se va a recuperar no es una zona horaria personalizada, intente crear una instancia de ella con el método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>.

2. Cree una instancia de un objeto <xref:System.Resources.ResourceManager> pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.

   Si no puede determinar el nombre completo del archivo de recursos incrustado, use [Ildasm. exe (desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado. Una entrada `.mresource` identifica el recurso. En el ejemplo, el nombre completo del recurso es `SerializeTimeZoneData.SerializedTimeZones`.

   Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de zona horaria, puede recuperar una referencia a él llamando al método de <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> `static` (`Shared` en Visual Basic).

3. Si se produce un error en la llamada al método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> o si se va a crear una instancia de una zona horaria personalizada, recupere una cadena que contenga la zona horaria serializada llamando al método <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>.

4. Deserializa los datos de la zona horaria llamando al método <xref:System.TimeZoneInfo.FromSerializedString%2A>.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se deserializa un objeto <xref:System.TimeZoneInfo> almacenado en un archivo de recursos XML incrustado .NET.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Este código muestra el control de excepciones para asegurarse de que existe un objeto de <xref:System.TimeZoneInfo> necesario para la aplicación. En primer lugar, intenta crear una instancia de un objeto <xref:System.TimeZoneInfo> mediante su recuperación del registro mediante el método <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>. Si no se puede crear una instancia de la zona horaria, el código la recupera del archivo de recursos incrustado.

Dado que los datos de las zonas horarias personalizadas (zonas horarias a las que se ha creado una instancia mediante el método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>) no se almacenan en el registro, el código no llama al <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para crear una instancia de la zona horaria de Palmer, Antártida. En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes de llamar al método <xref:System.TimeZoneInfo.FromSerializedString%2A>.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Guardado de zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
