---
title: "C&#243;mo: Enumerar zonas horarias presentes en un equipo | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enumerar zonas horarias [.NET Framework]"
  - "zonas horarias [.NET Framework], enumerar"
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Enumerar zonas horarias presentes en un equipo
Para trabajar correctamente con una zona horaria designada, es necesario que la información sobre esa zona horaria esté disponible para el sistema.  Los sistemas operativos Windows Vista y Windows XP almacenan esta información en el Registro.  Sin embargo, aunque el número total de zonas horarias que existen en el mundo es grande, el Registro sólo contiene información de un subconjunto de ellas.  Además, el propio Registro es una estructura dinámica cuyo contenido está sujeto a cambios intencionados y accidentales.  Como resultado, una aplicación no puede suponer siempre que una zona horaria determinada esté definida y disponible en un sistema.  El primer paso para muchas aplicaciones que utilizan aplicaciones con información de zona horaria es determinar si las zonas horarias necesarias están disponibles en el sistema local, o proporcionar una lista de zonas horarias para que el usuario seleccione.  Para ello, una aplicación debe enumerar las zonas horarias definidas en un sistema local.  
  
> [!NOTE]
>  Si una aplicación confía en la presencia de una zona horaria determinada que podría no estar definida en un sistema local, la aplicación puede garantizar su presencia serializando y deserializando la información sobre la zona horaria.  Después, la zona horaria se puede agregar a un control de lista para que el usuario de la aplicación pueda seleccionarla.  Para obtener información detallada, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) y [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).  
  
### Para enumerar las zonas horarias presentes en el sistema local  
  
1.  Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>.  El método devuelve una colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica de objetos <xref:System.TimeZoneInfo>.  La propiedad <xref:System.TimeZoneInfo.DisplayName%2A> ordena las entradas de la colección.  Por ejemplo:  
  
     [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
     [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]  
  
2.  Enumere los objetos <xref:System.TimeZoneInfo> individuales de la colección utilizando un bucle `foreach` \(en C\#\) o un bucle `For Each`. `Next` \(en Visual Basic\) y realice los procesos necesarios en cada objeto.  Por ejemplo, el siguiente código enumera la colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> de objetos <xref:System.TimeZoneInfo> devuelta en el paso 1 y enumera el nombre para mostrar de cada zona horaria en la consola.  
  
     [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
     [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]  
  
### Para mostrar al usuario una lista de zonas horarias presentes en el sistema local  
  
1.  Llame al método <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=fullName>.  El método devuelve una colección <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica de objetos <xref:System.TimeZoneInfo>.  
  
2.  Asigne la colección devuelta en el paso 1 a la propiedad `DataSource` de un control de formularios Windows Forms o de un control de lista de ASP.NET.  
  
3.  Recupere el objeto <xref:System.TimeZoneInfo> que el usuario ha seleccionado.  
  
 En el ejemplo se muestra una ilustración de una aplicación para Windows.  
  
## Ejemplo  
 En el ejemplo se inicia una aplicación para Windows que muestra las zonas horarias definidas en un sistema en un cuadro de lista.  A continuación, se muestra un cuadro de diálogo que contiene el valor de la propiedad <xref:System.TimeZoneInfo.DisplayName%2A> del objeto de zona horaria seleccionado por el usuario.  
  
 [!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
 [!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]  
  
 La mayoría de los controles de lista \(como el control <xref:System.Windows.Forms.ListBox?displayProperty=fullName> o <xref:System.Web.UI.WebControls.BulletedList?displayProperty=fullName> \) permiten asignar una colección de variables de objeto a su propiedad `DataSource` siempre que esa colección implemente la interfaz <xref:System.Collections.IEnumerable>. \(La clase <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> genérica realiza esta acción\). Para mostrar un objeto individual de la colección, el control llama al método `ToString` de ese objeto para extraer la cadena utilizada para representar el objeto.  En el caso de objetos <xref:System.TimeZoneInfo>, el método `ToString` devuelve el nombre para mostrar <xref:System.TimeZoneInfo> del objeto \(el valor de su propiedad <xref:System.TimeZoneInfo.DisplayName%2A>\).  
  
> [!NOTE]
>  Debido a que los controles de lista llaman al método `ToString` de un objeto, puede asignar una colección de objetos <xref:System.TimeZoneInfo> al control, hacer que el control muestre un nombre descriptivo para cada objeto, y recuperar el objeto <xref:System.TimeZoneInfo> que el usuario ha seleccionado.  Esto elimina la necesidad de extraer una cadena para cada objeto de la colección, asignar la cadena a una colección que, a su vez, está asignada a la propiedad `DataSource` del control, recuperar la cadena que el usuario ha seleccionado y, a continuación, utilizar esta cadena para extraer el objeto que describe.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importen los siguientes espacios de nombres:  
  
     <xref:System> \(en código de C\#\)  
  
     <xref:System.Collections.ObjectModel>  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)   
 [Cómo: Restaurar zonas horarias de un recurso incrustado](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)