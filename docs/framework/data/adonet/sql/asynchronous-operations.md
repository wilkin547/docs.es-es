---
title: Operaciones asincrónicas
ms.date: 03/30/2017
ms.assetid: e7d32c3c-bf78-4bfc-a357-c9e82e4a4b3c
ms.openlocfilehash: c104176d92667d7c8e2dc83c33bf3eb566437d7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918124"
---
# <a name="asynchronous-operations"></a>Operaciones asincrónicas
Algunas operaciones de base de datos, como las ejecuciones de comandos, pueden tardar bastante tiempo en completarse. En estos casos, las aplicaciones de un único subproceso deben bloquear otras operaciones y esperar a que el comando termine antes de poder continuar sus propias operaciones. En contraposición, la posibilidad de asignar la operación cuya ejecución tiene una larga duración a un subproceso en segundo plano permite que el subproceso en primer plano permanezca activo durante toda la operación. En las aplicaciones Windows, por ejemplo, delegar aquellas operaciones cuya ejecución tiene una larga duración en subprocesos en segundo plano permite que el subproceso de interfaz de usuario permanezca alerta mientras se ejecuta la operación.  
  
 .NET Framework proporciona varios patrones de diseño asincrónicos estándar que pueden utilizar los programadores para aprovechar los subprocesos en segundo plano y liberar a los subprocesos de interfaz de usuario o de alta prioridad para que completen otras operaciones. ADO.NET admite estos mismos patrones de diseño en su clase <xref:System.Data.SqlClient.SqlCommand>. En concreto, los métodos <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A> y <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A>, acompañados de los métodos <xref:System.Data.SqlClient.SqlCommand.EndExecuteNonQuery%2A>, <xref:System.Data.SqlClient.SqlCommand.EndExecuteReader%2A> y <xref:System.Data.SqlClient.SqlCommand.EndExecuteXmlReader%2A>, proporcionan la compatibilidad asincrónica.  
  
> [!NOTE]
> La programación asincrónica es una característica fundamental de .NET Framework, y ADO.NET aprovecha los patrones de diseño estándar. Para obtener más información sobre las diferentes técnicas asincrónicas disponibles para los desarrolladores, consulte [llamar a métodos sincrónicos de forma asincrónica](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
 Aunque el uso de técnicas asincrónicas con las características de ADO.NET no agrega ninguna consideración especial, es probable que más programadores utilicen las características asincrónicas en ADO.NET que en otras áreas de .NET Framework. Es importante tener en cuenta las ventajas e inconvenientes de crear aplicaciones multithreading. Los ejemplos que a continuación se muestran en esta sección señalan varios aspectos importantes que deben tener en cuenta los programadores al compilar aplicaciones que incorporan funcionalidad multithreading.  
  
## <a name="in-this-section"></a>En esta sección  
 [Aplicaciones Windows que usan devoluciones de llamada](../../../../../docs/framework/data/adonet/sql/windows-applications-using-callbacks.md)  
 Proporciona un ejemplo en el que se muestra cómo ejecutar un comando asincrónico de forma segura y controlar correctamente la interacción con un formulario y su contenido desde un subproceso independiente.  
  
 [Aplicaciones ASP.NET que usan identificadores de espera](../../../../../docs/framework/data/adonet/sql/aspnet-apps-using-wait-handles.md)  
 Proporciona un ejemplo en el que se muestra cómo ejecutar varios comandos simultáneos desde una página de ASP.NET, mediante el uso de controladores de espera que administran la operación al completarse todos los comandos.  
  
 [Sondeo de aplicaciones de consola](../../../../../docs/framework/data/adonet/sql/polling-in-console-applications.md)  
 Proporciona un ejemplo en el que se muestra el uso del sondeo para esperar a que se complete la ejecución de un comando asincrónico desde una aplicación de consola. Esta técnica también es válida en una biblioteca de clases u otra aplicación sin una interfaz de usuario.  
  
## <a name="see-also"></a>Vea también

- [SQL Server y ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [Llamada a métodos sincrónicos de forma asincrónica](../../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
