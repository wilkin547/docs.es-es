---
title: Mejoras de rendimiento de socket en la versión 3.5
description: Obtenga información sobre las mejoras de rendimiento de la clase System.Net.Sockets.Socket en .NET Framework 3.5.
ms.date: 03/30/2017
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
ms.openlocfilehash: 5bd7c97d6a6edd5f914d6fe3118b6d81b64544e0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263144"
---
# <a name="socket-performance-enhancements-in-version-35"></a>Mejoras de rendimiento de socket en la versión 3.5

En la versión 3.5 se ha mejorado la clase <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> para su uso por parte de aplicaciones que usan la E/S de red asincrónica para lograr el máximo rendimiento. Se han agregado una serie de clases como parte de un conjunto de mejoras de la clase <xref:System.Net.Sockets.Socket> que proporcionan un patrón asincrónico alternativo que pueden usar las aplicaciones de socket de alto rendimiento especializadas. Estas mejoras se han diseñado específicamente para las aplicaciones de servidor de red que necesitan un alto rendimiento. Una aplicación puede usar el patrón asincrónico mejorado exclusivamente o solo en áreas activas de destino de su aplicación (al recibir grandes cantidades de datos, por ejemplo).  
  
## <a name="class-enhancements"></a>Mejoras de clase  

 La característica principal de estas mejoras es la elusión de la asignación y la sincronización repetidas de objetos durante la E/S de socket asincrónico de gran volumen. El patrón de diseño de principio o final actualmente implementado por la clase <xref:System.Net.Sockets.Socket> para la E/S de socket asincrónico exige asignar un objeto <xref:System.IAsyncResult?displayProperty=nameWithType> para cada operación de socket asincrónico.  
  
 En las nuevas mejoras de la clase <xref:System.Net.Sockets.Socket>, las operaciones de socket asincrónico se describen mediante objetos reutilizables de la clase <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType> asignados y mantenidos por la aplicación. Las aplicaciones de socket de alto rendimiento saben mejor la cantidad de operaciones de socket superpuestas que se deben mantener. La aplicación puede crear tantos objetos <xref:System.Net.Sockets.SocketAsyncEventArgs> como necesite. Por ejemplo, si una aplicación de servidor necesita tener 15 operaciones de aceptación de socket pendientes en todo momento para admitir velocidades de conexión de cliente entrantes, puede asignar 15 objetos reutilizables <xref:System.Net.Sockets.SocketAsyncEventArgs> de antemano para ese fin.  
  
 El patrón para realizar una operación de socket asincrónico con esta clase consta de los pasos siguientes:  
  
1. Asigne un nuevo objeto de contexto <xref:System.Net.Sockets.SocketAsyncEventArgs> u obtenga uno libre de un grupo de aplicaciones.  
  
2. Establezca propiedades en el objeto de contexto para la operación que se va a realizar (el método delegado de devolución de llamada y el búfer de datos, por ejemplo).  
  
3. Llame al método de socket adecuado (xxxAsync) para iniciar la operación asincrónica.  
  
4. Si el método de socket asincrónico (xxxAsync) devuelve true en la devolución de llamada, consulte el estado de finalización en las propiedades de contexto.  
  
5. Si el método de socket asincrónico (xxxAsync) devuelve false en la devolución de llamada, la operación se ha completado de forma sincrónica. Para ver el resultado de la operación se pueden consultar las propiedades de contexto.  
  
6. Vuelva a usar el contexto para otra operación, vuelva a colocarlo en el grupo o descártelo.  
  
 La duración del nuevo objeto de contexto de operación de socket asincrónico está determinada por las referencias en el código de aplicación y las referencias de E/S asincrónicas. No es necesario que la aplicación conserve una referencia a un objeto de contexto de operación de socket asincrónico una vez que se ha enviado como parámetro a uno de los métodos de operación de socket asincrónico. La referencia se conserva hasta que se devuelve la devolución de llamada de finalización. Pero para la aplicación supone una ventaja conservar la referencia al objeto de contexto para poderla reutilizar para una operación de socket asincrónico futura.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SendPacketsElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=nameWithType>
- [Network Programming Samples (Ejemplos de programación de red)](network-programming-samples.md)
- [Ejemplos de código de socket](socket-code-examples.md)
