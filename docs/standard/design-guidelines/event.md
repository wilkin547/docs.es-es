---
title: "Dise&#241;o de eventos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "eventos anteriores"
  - "eventos [.NET Framework], instrucciones de diseño"
  - "instrucciones de diseño de miembros, eventos"
  - "controladores de eventos [.NET Framework], instrucciones de diseño de eventos"
  - "eventos posteriores"
  - "firmas, control de eventos"
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Dise&#241;o de eventos
Los eventos son la forma más utilizada de devoluciones de llamada \(construcciones que permiten que el marco de trabajo llamar a código de usuario\). Otros mecanismos de devolución de llamada incluyen a miembros tomar delegados, los miembros virtuales y los complementos basado en la interfaz. Datos de estudios de uso indican que la mayoría de los desarrolladores es más cómodo utilizar eventos que utilizan otros mecanismos de devolución de llamada. Eventos se integran perfectamente con Visual Studio y muchos idiomas.  
  
 Es importante tener en cuenta que hay dos grupos de eventos: eventos producidos antes de un estado de los cambios del sistema, denominados eventos anteriores y eventos generados después de un estado cambia, denominan eventos posteriores. Un ejemplo de un evento previo sería `Form.Closing`, que se desencadena antes de que se cierra un formulario. Un ejemplo de un evento posterior sería `Form.Closed`, que se provoca cuando se cierra un formulario.  
  
 **✓ hacer** utiliza el término "elevar" para los eventos en lugar de "activar" o "activar".  
  
 **✓ hacer** use <xref:System.EventHandler%601?displayProperty=fullName> en lugar de crear manualmente nuevos delegados que se usará como controladores de eventos.  
  
 **✓ considere** usando una subclase de <xref:System.EventArgs> como el argumento de evento, a menos que esté absolutamente seguro nunca tendrá que llevar los datos al método de control de eventos al evento en cuyo caso puede utilizar la `EventArgs` escribir directamente.  
  
 Si incluye una API con `EventArgs` directamente, nunca podrá agregar los datos se realice con el evento sin interrumpir la compatibilidad. Si usa una subclase, incluso si inicialmente completamente vacía, podrá agregar propiedades a la subclase cuando sea necesario.  
  
 **✓ hacer** utilizar un método virtual protegido para provocar cada evento. Esto solo es aplicable a los eventos no estáticos en clases no selladas, no a las estructuras, clases selladas ni eventos estáticos.  
  
 El propósito del método es proporcionar una forma de una clase derivada para controlar el evento mediante una invalidación. Reemplazar es la forma más natural, más rápida y más flexible para controlar los eventos de la clase base en clases derivadas. Por convención, el nombre del método debe comenzar con "On" y seguir con el nombre del evento.  
  
 La clase derivada puede elegir no llamar a la implementación base del método en su reemplazo. Prepárese para esto, no incluya ningún procesamiento en el método que se requiere para la clase base para que funcione correctamente.  
  
 **✓ hacer** tomar un parámetro al método protegido que genera un evento.  
  
 El parámetro se debe denominar `e` y debe escribirse como la clase de argumento de evento.  
  
 **X no** pase null como el remitente cuando se provoca un evento no estático.  
  
 **✓ hacer** pase null como el remitente al generar un evento estático.  
  
 **X no** pasa null como parámetro de datos del evento al iniciar un evento.  
  
 Debería pasar `EventArgs.Empty` Si no desea pasar ningún dato al método de control de eventos. Los desarrolladores esperan este parámetro no sea null.  
  
 **✓ considere** generar eventos que se puede cancelar el usuario final. Esto sólo se aplica a los eventos anteriores.  
  
 Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName> o su subclase como el argumento de evento para permitir al usuario final Cancelar eventos.  
  
### Diseño de controlador de eventos personalizados  
 Hay casos en los que `EventHandler<T>` no se puede utilizar, por ejemplo, cuando el marco de trabajo necesita trabajar con las versiones anteriores de CLR, que no era compatible con genéricos. En estos casos, tendrá que diseñar y desarrollar a un delegado de controlador de eventos personalizado.  
  
 **✓ hacer** utilizar un tipo de valor devuelto de void para los controladores de eventos.  
  
 Un controlador de eventos puede invocar varios métodos, posiblemente en varios objetos de control de eventos. Si se permiten métodos de control de eventos para devolver un valor, habrá varios valores devueltos para cada invocación del evento.  
  
 **✓ hacer** use `object` como el tipo del primer parámetro del controlador de eventos y llámelo `sender`.  
  
 **✓ hacer** use <xref:System.EventArgs?displayProperty=fullName> o su subclase como el tipo del segundo parámetro del controlador de eventos y llámelo `e`.  
  
 **X no** tiene más de dos parámetros en los controladores de eventos.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)