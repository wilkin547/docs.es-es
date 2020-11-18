---
title: Procedimiento para enumerar zonas horarias presentes en un equipo
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], enumerating
- enumerating time zones [.NET]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: 276c13bb95685e9588e25238f1a6e45cd57a6c91
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94817970"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Procedimiento para enumerar zonas horarias presentes en un equipo

Para trabajar correctamente con una zona horaria designada, es necesario que la información sobre esa zona horaria esté a disposición del sistema. Los sistemas operativos Windows XP y Windows Vista almacenan esta información en el registro. Pero aunque el número total de zonas horarias que existe en el mundo es elevado, el Registro contiene información sobre solo un subconjunto de ellas. Además, el propio Registro es una estructura dinámica cuyo contenido está sujeto a cambios intencionados y accidentales. Como resultado, una aplicación no siempre puede suponer que una zona horaria determinada esté definida y disponible en un sistema. El primer paso para muchas aplicaciones que usan aplicaciones de información de zona horaria es determinar si las zonas horarias necesarias están disponibles en el sistema local o proporcionar al usuario una lista de zonas horarias entre las que seleccionar. Esto exige que una aplicación enumere las zonas horarias definidas en un sistema local.

> [!NOTE]
> Si una aplicación se basa en la presencia de una zona horaria determinada que no se puede definir en un sistema local, la aplicación puede garantizar su presencia mediante la serialización y deserialización de la información sobre la zona horaria. A continuación, la zona horaria se puede Agregar a un control de lista para que el usuario de la aplicación pueda seleccionarla. Para obtener más información, consulte [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias desde un recurso incrustado](restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Para enumerar las zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección genérica de <xref:System.TimeZoneInfo> objetos. Las entradas de la colección se ordenan por su <xref:System.TimeZoneInfo.DisplayName%2A> propiedad. Por ejemplo:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerar los <xref:System.TimeZoneInfo> objetos individuales de la colección mediante un `foreach` bucle (en C#) o un `For Each` ...`Next` bucle (en Visual Basic) y realice cualquier procesamiento necesario en cada objeto. Por ejemplo, el código siguiente enumera la <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección de <xref:System.TimeZoneInfo> objetos devueltos en el paso 1 y muestra el nombre para mostrar de cada zona horaria en la consola.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Para presentar al usuario una lista de zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> colección genérica de <xref:System.TimeZoneInfo> objetos.

2. Asigne la colección devuelta en el paso 1 a la `DataSource` propiedad de un control de lista de Windows Forms o ASP.net.

3. Recupera el <xref:System.TimeZoneInfo> objeto que el usuario ha seleccionado.

En el ejemplo se muestra una ilustración para una aplicación Windows.

## <a name="example"></a>Ejemplo

En el ejemplo se inicia una aplicación de Windows que muestra las zonas horarias definidas en un sistema de un cuadro de lista. A continuación, en el ejemplo se muestra un cuadro de diálogo que contiene el valor de la <xref:System.TimeZoneInfo.DisplayName%2A> propiedad del objeto de zona horaria seleccionado por el usuario.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

La mayoría de los controles de lista (como el <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control o) le permiten asignar una colección de variables de objeto a su propiedad siempre que `DataSource` esa colección implemente la <xref:System.Collections.IEnumerable> interfaz. (La clase genérica lo <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> hace). Para mostrar un objeto individual en la colección, el control llama al método del objeto `ToString` para extraer la cadena que se utiliza para representar el objeto. En el caso de los <xref:System.TimeZoneInfo> objetos, el `ToString` método devuelve el <xref:System.TimeZoneInfo> nombre para mostrar del objeto (el valor de su <xref:System.TimeZoneInfo.DisplayName%2A> propiedad).

> [!NOTE]
> Dado que los controles de lista llaman al método de un objeto `ToString` , puede asignar una colección de <xref:System.TimeZoneInfo> objetos al control, hacer que el control muestre un nombre descriptivo para cada objeto y recuperar el <xref:System.TimeZoneInfo> objeto que el usuario ha seleccionado. Esto elimina la necesidad de extraer una cadena para cada objeto de la colección, asignar la cadena a una colección que, a su vez, se asigna a la propiedad del control `DataSource` , recuperar la cadena que el usuario ha seleccionado y, a continuación, utilizar esta cadena para extraer el objeto que describe.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se importen los espacios de nombres siguientes:

  <xref:System> (en código C#)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](index.md)
- [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md)
- [Cómo: restaurar zonas horarias de un recurso incrustado](restore-time-zones-from-an-embedded-resource.md)
