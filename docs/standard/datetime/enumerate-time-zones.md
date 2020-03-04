---
title: 'Cómo: enumerar zonas horarias presentes en un equipo'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
ms.openlocfilehash: aa8962c8aea208778983610041937dc3f75c1f1e
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159447"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>Cómo: enumerar zonas horarias presentes en un equipo

Para trabajar correctamente con una zona horaria designada, es necesario que la información sobre esa zona horaria esté a disposición del sistema. Los sistemas operativos Windows XP y Windows Vista almacenan esta información en el registro. Pero aunque el número total de zonas horarias que existe en el mundo es elevado, el Registro contiene información sobre solo un subconjunto de ellas. Además, el propio Registro es una estructura dinámica cuyo contenido está sujeto a cambios intencionados y accidentales. Como resultado, una aplicación no siempre puede suponer que una zona horaria determinada esté definida y disponible en un sistema. El primer paso para muchas aplicaciones que usan aplicaciones de información de zona horaria es determinar si las zonas horarias necesarias están disponibles en el sistema local o proporcionar al usuario una lista de zonas horarias entre las que seleccionar. Esto exige que una aplicación enumere las zonas horarias definidas en un sistema local.

> [!NOTE]
> Si una aplicación se basa en la presencia de una zona horaria determinada que no se puede definir en un sistema local, la aplicación puede garantizar su presencia mediante la serialización y deserialización de la información sobre la zona horaria. A continuación, la zona horaria se puede Agregar a un control de lista para que el usuario de la aplicación pueda seleccionarla. Para obtener más información, consulte [Cómo: guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: restaurar zonas horarias desde un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>Para enumerar las zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una colección genérica de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> de objetos <xref:System.TimeZoneInfo>. Las entradas de la colección se ordenan por su propiedad <xref:System.TimeZoneInfo.DisplayName%2A>. Por ejemplo:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. Enumerar los objetos <xref:System.TimeZoneInfo> individuales de la colección mediante un bucle `foreach` (en C#) o un `For Each`...`Next` bucle (en Visual Basic) y realice cualquier procesamiento necesario en cada objeto. Por ejemplo, el código siguiente enumera la colección de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> de objetos <xref:System.TimeZoneInfo> devueltos en el paso 1 y muestra el nombre para mostrar de cada zona horaria en la consola.

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>Para presentar al usuario una lista de zonas horarias presentes en el sistema local

1. Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType>. El método devuelve una colección genérica de <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> de objetos <xref:System.TimeZoneInfo>.

2. Asigne la colección devuelta en el paso 1 a la propiedad `DataSource` de un control de lista de Windows Forms o ASP.NET.

3. Recupera el objeto de <xref:System.TimeZoneInfo> que ha seleccionado el usuario.

En el ejemplo se muestra una ilustración para una aplicación Windows.

## <a name="example"></a>Ejemplo

En el ejemplo se inicia una aplicación de Windows que muestra las zonas horarias definidas en un sistema de un cuadro de lista. A continuación, en el ejemplo se muestra un cuadro de diálogo que contiene el valor de la propiedad <xref:System.TimeZoneInfo.DisplayName%2A> del objeto de zona horaria seleccionado por el usuario.

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

La mayoría de los controles de lista (como el control <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> o <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>) le permiten asignar una colección de variables de objeto a su propiedad `DataSource`, siempre y cuando dicha colección implemente la interfaz de <xref:System.Collections.IEnumerable>. (La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica lo hace). Para mostrar un objeto individual en la colección, el control llama al método `ToString` del objeto para extraer la cadena que se utiliza para representar el objeto. En el caso de <xref:System.TimeZoneInfo> objetos, el método `ToString` devuelve el nombre para mostrar del objeto <xref:System.TimeZoneInfo> (el valor de su propiedad <xref:System.TimeZoneInfo.DisplayName%2A>).

> [!NOTE]
> Dado que los controles de lista llaman al método `ToString` de un objeto, se puede asignar una colección de objetos <xref:System.TimeZoneInfo> al control, hacer que el control muestre un nombre descriptivo para cada objeto y recuperar el objeto <xref:System.TimeZoneInfo> que ha seleccionado el usuario. Esto elimina la necesidad de extraer una cadena para cada objeto de la colección, asignar la cadena a una colección que, a su vez, se asigna a la propiedad `DataSource` del control, recuperar la cadena que el usuario ha seleccionado y, a continuación, utilizar esta cadena para extraer el objeto que describe.

## <a name="compiling-the-code"></a>Compilación del código

Para este ejemplo se necesita:

- Que se importen los espacios de nombres siguientes:

  <xref:System> (en C# código)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>Vea también

- [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)
- [Guardado de zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [Restauración de zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
