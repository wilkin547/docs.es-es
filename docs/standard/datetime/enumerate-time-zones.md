---
title: Procedimiento para enumerar zonas horarias presentes en un equipo
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82898e80f5acb2cb0dcab65390701efc8d48115b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586566"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedimiento para enumerar zonas horarias presentes en un equipo

Para trabajar correctamente con una zona horaria designada, es necesario que la información sobre esa zona horaria esté a disposición del sistema. Los sistemas operativos Windows XP y Windows Vista almacenar esta información en el registro. Pero aunque el número total de zonas horarias que existe en el mundo es elevado, el Registro contiene información sobre solo un subconjunto de ellas. Además, el propio Registro es una estructura dinámica cuyo contenido está sujeto a cambios intencionados y accidentales. Como resultado, una aplicación no siempre puede suponer que una zona horaria determinada esté definida y disponible en un sistema. El primer paso para muchas aplicaciones que usan aplicaciones de información de zona horaria es determinar si las zonas horarias necesarias están disponibles en el sistema local o proporcionar al usuario una lista de zonas horarias entre las que seleccionar. Esto exige que una aplicación enumere las zonas horarias definidas en un sistema local.

> [!NOTE]
> Si una aplicación se basa en la presencia de una zona horaria determinada que no se pueden definir en un sistema local, la aplicación puede garantizar su presencia si serializar y deserializar la información sobre la zona horaria. La zona horaria, a continuación, se pueden agregar a un control de lista para que el usuario de la aplicación puede seleccionarla. Para obtener más detalles, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Para enumerar las zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve un tipo genérico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección de <xref:System.TimeZoneInfo> objetos. Las entradas de la colección se ordenan por sus <xref:System.TimeZoneInfo.DisplayName%2A> propiedad. Por ejemplo:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerar el individuo <xref:System.TimeZoneInfo> objetos de la colección mediante el uso de un `foreach` bucle (en C#) o un `For Each`...`Next` bucle (en Visual Basic) y realizar cualquier procesamiento necesario en cada objeto. Por ejemplo, el código siguiente enumera los <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección de <xref:System.TimeZoneInfo> objetos devuelta en el paso 1 y enumera el nombre para mostrar de cada zona horaria en la consola.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Para presentar al usuario una lista de zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve un tipo genérico <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección de <xref:System.TimeZoneInfo> objetos.

2. Asignar la colección devuelta en el paso 1 para el `DataSource` propiedad de un Windows forms o ASP.NET control de lista.

3. Recuperar el <xref:System.TimeZoneInfo> objeto que el usuario ha seleccionado.

El ejemplo proporciona una ilustración de una aplicación de Windows.

## <a name="example"></a>Ejemplo

El ejemplo inicia una aplicación de Windows que muestra las zonas horarias definidas en un sistema en un cuadro de lista. En el ejemplo, a continuación, muestra un cuadro de diálogo que contiene el valor de la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad del objeto de zona horaria seleccionado por el usuario.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

Más controles de lista (como el <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> o <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) permiten asignar una colección de variables de objeto para sus `DataSource` propiedad siempre y cuando esa colección implementa la <xref:System.Collections.IEnumerable> interfaz. (La interfaz genérica <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> clase hace esto.) Para mostrar un objeto individual de la colección, el control llama a ese objeto `ToString` método para extraer la cadena que se usa para representar el objeto. En el caso de <xref:System.TimeZoneInfo> objetos, el `ToString` método devuelve el <xref:System.TimeZoneInfo> nombre para mostrar del objeto (el valor de su <xref:System.TimeZoneInfo.DisplayName%2A> propiedad).

> [!NOTE]
> Dado que los controles de lista, llamar a un objeto `ToString` método, puede asignar una colección de <xref:System.TimeZoneInfo> objetos al control, que el control muestre un nombre descriptivo para cada objeto y recuperar el <xref:System.TimeZoneInfo> objeto que el usuario ha seleccionado. Esto elimina la necesidad de extraer una cadena para cada objeto de la colección, asignar la cadena a una colección que se asigna a su vez para el control `DataSource` propiedad, recupere la cadena que el usuario ha seleccionado y, a continuación, usar esta cadena para extraer el objeto que describe. 

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

* Que se importarán los espacios de nombres siguientes:

  <xref:System> (en el código de C#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
