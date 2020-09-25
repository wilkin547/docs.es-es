---
title: Operaciones asincrónicas
ms.date: 03/30/2017
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
ms.openlocfilehash: f94a33b1ff06b5433f61687b8e28096ea37b412a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197591"
---
# <a name="asynchronous-operations"></a>Operaciones asincrónicas

Algunas operaciones de base de datos, como las ejecuciones de comandos, pueden tardar mucho tiempo en completarse. En estos casos, las aplicaciones con un único subproceso deben bloquear otras operaciones y esperar hasta que el comando finaliza antes de continuar con otras operaciones. En cambio, el poder asignar la operación de ejecución prolongada a un subproceso en segundo plano permite que el subproceso en primer plano permanezca activo durante toda la operación. En una aplicación Windows, por ejemplo, delegar la operación de larga duración a un subproceso en segundo plano permite que el subproceso de la interfaz de usuario siga respondiendo.  
  
 .NET Framework proporciona varios patrones de diseño asincrónicos estándar que pueden utilizar los programadores para aprovechar los subprocesos en segundo plano y liberar a los subprocesos de interfaz de usuario o de alta prioridad para que completen otras operaciones. ADO.NET admite estos mismos patrones de diseño en su clase <xref:System.Data.SqlClient.SqlCommand>. En concreto, los métodos <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> y <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A>, emparejados con los métodos <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> y <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A>, proporcionan la compatibilidad asincrónica.  
  
> [!NOTE]
> La programación asincrónica es una característica fundamental de .NET Framework, y ADO.NET aprovecha los patrones de diseño estándar. Para obtener más información sobre las diferentes técnicas asincrónicas disponibles para los desarrolladores, vea el artículo sobre cómo [llamar a métodos sincrónicos de forma asincrónica](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Aunque el uso de técnicas asincrónicas con las características de ADO.NET no agrega ninguna consideración especial, es probable que más programadores utilicen las características asincrónicas en ADO.NET que en otras áreas de .NET Framework. Es importante tener en cuenta las ventajas e inconvenientes de crear aplicaciones multithreading. En los ejemplos siguientes de esta sección se indican varios problemas importantes que los desarrolladores deben tener en cuenta al crear aplicaciones que incorporan funcionalidades multiproceso.  
  
## <a name="in-this-section"></a>En esta sección  

 [Aplicaciones Windows que usan devoluciones de llamada](windows-applications-using-callbacks.md)  
 Proporciona un ejemplo en el que se muestra cómo ejecutar un comando asincrónico de forma segura, controlando correctamente la interacción con un formulario y su contenido desde un subproceso independiente.  
  
 [Aplicaciones ASP.NET con identificadores de espera](aspnet-apps-using-wait-handles.md)  
 Proporciona un ejemplo en el que se muestra cómo ejecutar varios comandos simultáneos desde una página ASP.NET. Para ello, se usan identificadores Wait para administrar la operación cuando se completan todos los comandos.  
  
 [Sondear aplicaciones de consola](polling-in-console-applications.md)  
 Proporciona un ejemplo que muestra el uso del sondeo para esperar a que se complete la ejecución de un comando asincrónico desde una aplicación de consola. Esta técnica también es válida en una biblioteca de clases u otra aplicación sin una interfaz de usuario.  
  
## <a name="see-also"></a>Consulte también

- [SQL Server y ADO.NET](index.md)
- [Llamada a métodos sincrónicos de forma asincrónica](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)
- [Información general de ADO.NET](../ado-net-overview.md)
