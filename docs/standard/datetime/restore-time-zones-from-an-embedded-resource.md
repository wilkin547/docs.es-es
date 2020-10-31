---
title: Procedimiento para restaurar zonas horarias de un recurso incrustado
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: 1dd3dff2441ac5e21f3ebf97d58919a7c65d42c5
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063435"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Procedimiento para restaurar zonas horarias de un recurso incrustado

En este tema se describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos. Para obtener información e instrucciones sobre cómo guardar zonas horarias, consulte [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md).

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Para deserializar un objeto TimeZoneInfo desde un recurso incrustado

1. Si la zona horaria que se va a recuperar no es una zona horaria personalizada, intente crear una instancia de ella mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.

2. Cree una instancia <xref:System.Resources.ResourceManager> de un objeto pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.

   Si no puede determinar el nombre completo del archivo de recursos incrustado, use el [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado. Una `.mresource` entrada identifica el recurso. En el ejemplo, el nombre completo del recurso es `SerializeTimeZoneData.SerializedTimeZones` .

   Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de zona horaria, puede recuperar una referencia a él llamando al `static` `Shared` método (en Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .

3. Si se produce un error en la llamada al <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método o si se va a crear una instancia de una zona horaria personalizada, recupere una cadena que contenga la zona horaria serializada llamando al <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> método.

4. Deserializa los datos de la zona horaria llamando al <xref:System.TimeZoneInfo.FromSerializedString%2A> método.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se deserializa un <xref:System.TimeZoneInfo> objeto almacenado en un archivo de recursos de .net XML incrustado.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Este código muestra el control de excepciones para asegurarse de que <xref:System.TimeZoneInfo> existe un objeto requerido por la aplicación. Primero se intenta crear una instancia <xref:System.TimeZoneInfo> de un objeto mediante la recuperación del registro mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método. Si no se puede crear una instancia de la zona horaria, el código la recupera del archivo de recursos incrustado.

Dado que los datos de las zonas horarias personalizadas (zonas horarias a las que se ha creado una instancia mediante el <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método) no se almacenan en el registro, el código no llama <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> a para crear una instancia de la zona horaria de Palmer, Antártida. En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes de llamar al <xref:System.TimeZoneInfo.FromSerializedString%2A> método.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se va a agregar al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Consulte también

- [Fechas, horas y zonas horarias](index.md)
- [Información general sobre zonas horarias](time-zone-overview.md)
- [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md)
