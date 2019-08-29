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
ms.openlocfilehash: afc3b57659dd6719f72cefba8a6d2f1abe08c0d0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106650"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedimiento para enumerar zonas horarias presentes en un equipo

Para trabajar correctamente con una zona horaria designada, es necesario que la información sobre esa zona horaria esté a disposición del sistema. Los sistemas operativos Windows XP y Windows Vista almacenan esta información en el registro. Pero aunque el número total de zonas horarias que existe en el mundo es elevado, el Registro contiene información sobre solo un subconjunto de ellas. Además, el propio Registro es una estructura dinámica cuyo contenido está sujeto a cambios intencionados y accidentales. Como resultado, una aplicación no siempre puede suponer que una zona horaria determinada esté definida y disponible en un sistema. El primer paso para muchas aplicaciones que usan aplicaciones de información de zona horaria es determinar si las zonas horarias necesarias están disponibles en el sistema local o proporcionar al usuario una lista de zonas horarias entre las que seleccionar. Esto exige que una aplicación enumere las zonas horarias definidas en un sistema local.

> [!NOTE]
> Si una aplicación se basa en la presencia de una zona horaria determinada que no se puede definir en un sistema local, la aplicación puede garantizar su presencia mediante la serialización y deserialización de la información sobre la zona horaria. A continuación, la zona horaria se puede Agregar a un control de lista para que el usuario de la aplicación pueda seleccionarla. Para obtener más detalles, vea [Cómo: Guardar zonas horarias en un recurso](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) incrustado y [cómo: Restaure las zonas horarias de](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)un recurso incrustado.

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Para enumerar las zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica de <xref:System.TimeZoneInfo> objetos. Las entradas de la colección se ordenan por su <xref:System.TimeZoneInfo.DisplayName%2A> propiedad. Por ejemplo:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerar los objetos <xref:System.TimeZoneInfo> individuales de la colección mediante un `foreach` bucle (en C#) o un `For Each`...`Next` bucle (en Visual Basic) y realice cualquier procesamiento necesario en cada objeto. Por ejemplo, el código siguiente enumera la <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección de <xref:System.TimeZoneInfo> objetos devueltos en el paso 1 y muestra el nombre para mostrar de cada zona horaria en la consola.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Para presentar al usuario una lista de zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica de <xref:System.TimeZoneInfo> objetos.

2. Asigne la colección devuelta en el paso 1 `DataSource` a la propiedad de un control de lista de Windows Forms o ASP.net.

3. Recupera el <xref:System.TimeZoneInfo> objeto que el usuario ha seleccionado.

En el ejemplo se muestra una ilustración para una aplicación Windows.

## <a name="example"></a>Ejemplo

En el ejemplo se inicia una aplicación de Windows que muestra las zonas horarias definidas en un sistema de un cuadro de lista. A continuación, en el ejemplo se muestra un cuadro de diálogo que <xref:System.TimeZoneInfo.DisplayName%2A> contiene el valor de la propiedad del objeto de zona horaria seleccionado por el usuario.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

La mayoría de los controles de lista <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> ( <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> como el control o) le permiten asignar una colección de variables de `DataSource` objeto a su propiedad siempre que esa colección implemente la <xref:System.Collections.IEnumerable> interfaz. (La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica lo hace). Para mostrar un objeto individual en la colección, el control llama al método del `ToString` objeto para extraer la cadena que se utiliza para representar el objeto. En el caso de <xref:System.TimeZoneInfo> los objetos, `ToString` el método devuelve <xref:System.TimeZoneInfo> el nombre para mostrar del objeto (el valor <xref:System.TimeZoneInfo.DisplayName%2A> de su propiedad).

> [!NOTE]
> Dado que los controles de lista llaman `ToString` al método de un objeto, puede asignar <xref:System.TimeZoneInfo> una colección de objetos al control, hacer que el control muestre un nombre descriptivo para cada objeto y <xref:System.TimeZoneInfo> recuperar el objeto que el usuario ha seleccionado. Esto elimina la necesidad de extraer una cadena para cada objeto de la colección, asignar la cadena a una colección que, a su vez, se asigna a `DataSource` la propiedad del control, recuperar la cadena que el usuario ha seleccionado y, a continuación, utilizar esta cadena para extraer el objeto. que describe. 

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se importen los espacios de nombres siguientes:

  <xref:System>(en C# código)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Procedimientos: Restauración de zonas horarias desde un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
