---
title: Actualizaciones personalizadas de secuencias
ms.date: 03/30/2017
ms.assetid: e3da85c8-57f3-4e32-a4cb-50123f30fea6
ms.openlocfilehash: 3ef0f59a5d63c24188b29cb7a38db2d6323d80ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295590"
---
# <a name="custom-stream-upgrades"></a>Actualizaciones personalizadas de secuencias

Los transportes orientados a secuencia como TCP y las canalizaciones con nombre funcionan en una secuencia continua de bytes entre el cliente y servidor. Esta secuencia la realiza un objeto <xref:System.IO.Stream>. En una actualización de secuencia, el cliente desea agregar una capa de protocolo opcional a la pila del canal y pide al otro lado del canal de comunicación que lo haga. La actualización de secuencia consiste en reemplazar el objeto <xref:System.IO.Stream> original con uno actualizado.  
  
 Por ejemplo, puede crear directamente una secuencia de compresión encima de la secuencia de transporte. En este caso, el transporte <xref:System.IO.Stream> original se reemplaza con uno que encapsula la compresión <xref:System.IO.Stream> alrededor del original.  
  
 Puede aplicar varias actualizaciones de secuencia, cada una que encapsule a la precedente.  
  
## <a name="how-stream-upgrades-work"></a>Cómo funcionan las actualizaciones de secuencia  

 Hay cuatro componentes en el proceso de actualización de secuencia.  
  
1. Un *iniciador* de flujo de actualización comienza el proceso: en tiempo de ejecución puede iniciar una solicitud al otro extremo de su conexión para actualizar la capa de transporte del canal.  
  
2. Un *aceptador* de flujos de actualización lleva a cabo la actualización: en tiempo de ejecución recibe la solicitud de actualización desde el otro equipo y, si es posible, acepta la actualización.  
  
3. Un *proveedor* de actualización crea el *iniciador* en el cliente y el *aceptador* en el servidor.  
  
4. Se agrega un *elemento de enlace* de actualización de secuencia a los enlaces en el servicio y el cliente, y se crea el proveedor en tiempo de ejecución.  
  
 Observe que en el caso de varias actualizaciones, el iniciador y aceptador encapsulan las máquinas de estado para exigir qué transiciones de actualización son válidas para cada iniciación.  
  
## <a name="how-to-implement-a-stream-upgrade"></a>Cómo implementar una actualización de secuencia  

 Windows Communication Foundation (WCF) proporciona cuatro `abstract` clases que se pueden implementar:  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeInitiator?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeProvider?displayProperty=nameWithType>  
  
- <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement?displayProperty=nameWithType>  
  
 Para implementar una actualización de secuencia personalizada, haga lo siguiente. Este procedimiento implementa un proceso de actualización de secuencia mínimo en los equipos del servidor y del cliente.  
  
1. Cree una clase que implemente <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>.  
  
    1. Invalide el método <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.InitiateUpgrade%2A> para tomar la secuencia que se va a actualizar y devuelva la secuencia actualizada. Este método funciona sincrónicamente; hay métodos análogos para iniciar de forma asincrónica la actualización.  
  
    2. Invalide el método <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> para comprobar las actualizaciones adicionales.  
  
2. Cree una clase que implemente <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>.  
  
    1. Invalide el método <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.AcceptUpgrade%2A> para tomar la secuencia que se va a actualizar y devuelva la secuencia actualizada. Este método funciona sincrónicamente; hay métodos análogos para aceptar de forma asincrónica la actualización.  
  
    2. Invalide el método <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A> para determinar si este aceptador de actualización admite la actualización solicitada en el proceso de actualización.  
  
3. Cree una clase que implemente <xref:System.ServiceModel.Channels.StreamUpgradeProvider>. Invalide los métodos <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeAcceptor%2A> y <xref:System.ServiceModel.Channels.StreamUpgradeProvider.CreateUpgradeInitiator%2A> para devolver las instancias del aceptador e iniciador definidas en los pasos 2 y 1.  
  
4. Cree una clase que implemente <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>.  
  
    1. Invalide el método <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildClientStreamUpgradeProvider%2A> en el cliente y el método <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement.BuildServerStreamUpgradeProvider%2A> en el servicio.  
  
    2. Invalide el método <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> en el cliente y el método <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> en el servicio para agregar la actualización Elemento de enlace a <xref:System.ServiceModel.Channels.BindingContext.BindingParameters%2A>.  
  
5. Agregue el nuevo elemento de enlace de actualización de secuencia a los enlaces en los equipos del cliente y del servidor.  
  
## <a name="security-upgrades"></a>Actualizaciones de seguridad  

 Agregar una actualización de seguridad es una versión especializada del proceso de actualización de secuencia general.  
  
 WCF ya proporciona dos elementos de enlace para actualizar la seguridad de la secuencia. La configuración de la seguridad de nivel de transporte la encapsula <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> y <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>, que se pueden configurar y agregar a un enlace personalizado. Estos elementos de enlace extienden la clase <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement> que crea los proveedores de actualización de secuencia del cliente y el servidor. Estos elementos de enlace tienen métodos que crean las clases de proveedor de actualización de secuencia de seguridad especializadas, que no son `public`, por lo que para estos dos casos solamente se necesita agregar el elemento de enlace a este enlace.  
  
 Para los escenarios de seguridad que no se incluyan en los dos elementos de enlace anteriores, tres clases `abstract` relacionadas con seguridad se derivan de las clases base de iniciador, aceptador y proveedor anteriores:  
  
1. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator?displayProperty=nameWithType>  
  
2. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor?displayProperty=nameWithType>  
  
3. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider?displayProperty=nameWithType>  
  
 El proceso de implementar una actualización de secuencia de seguridad es igual que antes, con la diferencia de que derivaría de estas tres clases. Invalide las propiedades adicionales en estas clases para proporcionar información de seguridad al tiempo de ejecución.  
  
## <a name="multiple-upgrades"></a>Varias actualizaciones  

 Para crear solicitudes de actualización adicionales, repita el proceso arriba mencionado: cree extensiones adicionales de <xref:System.ServiceModel.Channels.StreamUpgradeProvider> y elementos de enlace. Agregue los elementos de enlace al enlace. Se procesan los elementos de enlace adicionales secuencialmente, empezando por el primer elemento de enlace agregado al enlace. En <xref:System.ServiceModel.Channels.BindingElement.BuildChannelFactory%2A> y <xref:System.ServiceModel.Channels.BindingElement.BuildChannelListener%2A> cada proveedor de actualización puede determinar cómo disponerse en capas en cualquiera de los parámetros de enlace de actualización ya existentes. Debería reemplazar a continuación el parámetro de enlace de actualización existente con un nuevo parámetro de enlace de actualización compuesta.  
  
 Alternativamente, un proveedor de actualización puede admitir varias actualizaciones. Por ejemplo, podría desear implementar un proveedor de actualización de secuencia personalizado que admita seguridad y compresión. Siga estos pasos:  
  
1. <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider> subclase para escribir la clase de proveedor que crea el iniciador y el aceptador.  
  
2. Cree subclase de <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator> asegurándose de invalidar el método <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> para devolver los tipos de contenido para la secuencia de compresión y la secuencia segura en orden.  
  
3. Cree subclase de <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor> que entienda los tipos de contenido personalizados en su método <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.  
  
4. La secuencia se actualizará después de cada llamada a <xref:System.ServiceModel.Channels.StreamUpgradeInitiator.GetNextUpgrade%2A> y <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor.CanUpgrade%2A>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.StreamUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeInitiator>
- <xref:System.ServiceModel.Channels.StreamUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeAcceptor>
- <xref:System.ServiceModel.Channels.StreamUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamSecurityUpgradeProvider>
- <xref:System.ServiceModel.Channels.StreamUpgradeBindingElement>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
