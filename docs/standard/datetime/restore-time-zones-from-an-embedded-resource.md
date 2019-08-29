---
title: Procedimiento para restaurar zonas horarias de un recurso incrustado
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
ms.openlocfilehash: 98813bf6685be78d33ebd5cc5e8c07a61a811c25
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106758"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>Procedimiento para restaurar zonas horarias de un recurso incrustado

En este tema se describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos. Para obtener información e instrucciones acerca de cómo guardar zonas [horarias, consulte Cómo: Guardar zonas horarias en un recurso](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)incrustado.

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>Para deserializar un objeto TimeZoneInfo desde un recurso incrustado

1. Si la zona horaria que se va a recuperar no es una zona horaria personalizada, intente crear una instancia de ella <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> mediante el método.

2. Cree una instancia <xref:System.Resources.ResourceManager> de un objeto pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.

   Si no puede determinar el nombre completo del archivo de recursos incrustado, use [Ildasm. exe (desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado. Una `.mresource` entrada identifica el recurso. En el ejemplo, el nombre completo del recurso es `SerializeTimeZoneData.SerializedTimeZones`.

   Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de zona horaria, puede recuperar una referencia `static` a`Shared` él llamando al <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> método (en Visual Basic).

3. Si se produce un error <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> en la llamada al método o si se va a crear una instancia de una zona horaria personalizada, recupere una cadena que contenga la zona <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> horaria serializada llamando al método.

4. Deserializa los datos de la zona horaria llamando al <xref:System.TimeZoneInfo.FromSerializedString%2A> método.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se deserializa <xref:System.TimeZoneInfo> un objeto almacenado en un archivo de recursos de .net XML incrustado.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

Este código muestra el control de excepciones para asegurarse de <xref:System.TimeZoneInfo> que existe un objeto requerido por la aplicación. Primero se intenta crear una instancia de <xref:System.TimeZoneInfo> un objeto mediante la recuperación del registro mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método. Si no se puede crear una instancia de la zona horaria, el código la recupera del archivo de recursos incrustado.

Dado <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> que los datos de las zonas horarias personalizadas (zonas horarias <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> a las que se ha creado una instancia mediante el método) no se almacenan en el registro, el código no llama a para crear una instancia de la zona horaria de Palmer, Antártida. En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes <xref:System.TimeZoneInfo.FromSerializedString%2A> de llamar al método.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.

- Que se importen los espacios de nombres siguientes:

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)
- [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
