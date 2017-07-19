---
title: "Mejoras de rendimiento de socket en la versi&#243;n 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Mejoras de rendimiento de socket en la versi&#243;n 3.5
La clase de <xref:System.Net.Sockets.Socket?displayProperty=fullName> se ha mejorado en la versión 3,5 para uso de las aplicaciones que utilizan E\/S asincrónica de red para lograr el rendimiento más alto.  Una serie de clases nuevas se ha agregado como parte de un conjunto de mejoras en la clase de <xref:System.Net.Sockets.Socket> que proporcionan un modelo asincrónico alternativo que puede ser utilizado por aplicaciones de alto rendimiento especializadas de socket.  Estas mejoras se han diseñado específicamente para las aplicaciones de servidor de red que necesitan alto rendimiento.  Una aplicación puede utilizar el modelo asincrónico mejorado exclusivamente, o sólo en áreas activas de destino de la aplicación \(al recibir una gran cantidad de datos, por ejemplo\).  
  
## Mejoras de la clase  
 La característica principal de estas mejoras es la anulación de la asignación repetida y la sincronización de objetos durante la E\/S de socket asincrónico de gran volumen de datos.  El inicio y el modelo realiza de diseño implementado actualmente por la clase de <xref:System.Net.Sockets.Socket> para la E\/S asincrónica de socket requiere un objeto de <xref:System.IAsyncResult?displayProperty=fullName> se asigna para cada operación asincrónica de socket.  
  
 En los nuevos mejoras de la clase de <xref:System.Net.Sockets.Socket> , las operaciones asincrónicas de socket se describen mediante la clase reutilizable de <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName> se oponen asignado y mantenido por la aplicación.  Las aplicaciones de socket de alto rendimiento conocen bien la cantidad de operaciones de socket superpuestas que se deben sostener.  La aplicación puede crear todos los objetos <xref:System.Net.Sockets.SocketAsyncEventArgs> que necesite.  Por ejemplo, si una aplicación de servidor necesita que el socket 15 acepte las operaciones excepcionales siempre para admitir tasas de entrada de la conexión de cliente, puede asignar 15 objetos reutilizables de <xref:System.Net.Sockets.SocketAsyncEventArgs> de antemano para ese propósito.  
  
 El modelo para realizar una operación de socket asincrónico con esta clase consta de los pasos siguientes:  
  
1.  Asigne un nuevo objeto de contexto <xref:System.Net.Sockets.SocketAsyncEventArgs> u obtenga uno gratuitamente de un grupo de aplicaciones.  
  
2.  Establezca las propiedades en el objeto de contexto a la operación alrededor que se va a realizar \(el método y el búfer de datos del delegado de devolución de llamada, por ejemplo\).  
  
3.  Llame al método de socket adecuado \(xxxAsync\) para iniciar la operación asincrónica.  
  
4.  Si el método asincrónico de socket \(xxxAsync\) devuelve true en la devolución, vea propiedades de contexto para el estado de finalización.  
  
5.  Si el método asincrónico de socket \(xxxAsync\) devuelve false en la devolución de llamada, la operación completa de forma sincrónica.  El resultado de la operación se puede consultar en las propiedades del contexto.  
  
6.  Reutilice el contexto para otra operación, vuélvalo a poner en el grupo o descártelo.  
  
 La duración del nuevo objeto asincrónico de contexto de la operación de socket viene determinada por referencias en las referencias de E\/S del código de aplicación y asincrónicas.  No es necesario que la aplicación retenga una referencia a un objeto de contexto de la operación de socket asincrónico una vez enviada como parámetro a uno de los métodos de la operación de socket asincrónico.  Se seguirá haciendo referencia a él hasta que se devuelva la devolución de llamada de finalización.  Sin embargo es de gran utilidad para que la aplicación mantenga la referencia al objeto de contexto para poder reutilizar para una operación asincrónica futura de socket.  
  
## Vea también  
 <xref:System.Net.Sockets.Socket?displayProperty=fullName>   
 <xref:System.Net.Sockets.SendPacketsElement?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=fullName>   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Ejemplo de tecnología de rendimiento de socket](http://go.microsoft.com/fwlink/?LinkID=179570)