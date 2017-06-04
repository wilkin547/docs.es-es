---
title: "Arquitectura de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "arquitectura [WCF]"
  - "WCF [WCF], arquitectura"
  - "Windows Communication Foundation [WCF], arquitectura"
ms.assetid: a3bcb0a1-56ea-4ba6-9736-d260d90dade5
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Arquitectura de Windows Communication Foundation
El gráfico siguiente muestra las capas principales de la arquitectura [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].  
  
## Arquitectura de WCF  
 ![Arquitectura WCF](../../../docs/framework/wcf/media/wcf-architecture.gif "WCF\_Architecture")  
  
### Contratos y descripciones  
 Los contratos definen varios aspectos del sistema de mensajes.El contrato de datos describe cada parámetro que constituye cada mensaje que un servicio puede crear o utilizar.Los documentos de Lenguaje de definición de esquemas XML \(XSD\) definen los parámetros de mensaje, permitiendo a cualquier sistema que entienda XML procesar los documentos.El contrato del mensaje define partes específicas del mensaje utilizando los protocolos SOAP y permite el control más fino sobre las partes del mensaje, cuando la interoperabilidad exige tal precisión.El contrato de servicios especifica las firmas de método actuales del servicio y se distribuye como una interfaz en uno de los lenguajes de programación compatibles, como Visual Basic o Visual C\#.  
  
 Las directivas y enlaces estipulan las condiciones exigidas para comunicarse con un servicio.Por ejemplo, el enlace debe especificar \(como mínimo\) el transporte utilizado \(por ejemplo, HTTP o TCP\) y una codificación.Las directivas incluyen los requisitos de seguridad y otras condiciones que se deben cumplir para comunicarse con un servicio.  
  
### Tiempo de ejecución de servicio  
 La capa del tiempo de ejecución del servicio contiene los comportamientos que solo se producen durante la operación actual del servicio, es decir, los comportamientos en tiempo de ejecución del servicio.La limitación de peticiones controla cuántos mensajes se procesan que puede variar si la demanda para el servicio crece a un límite preestablecido.Un comportamiento de error especifica lo que sucede cuando se produce un error interno en el servicio, por ejemplo, controlando qué información se comunica al cliente.\(Demasiada información puede dar ventaja a un usuario malintencionado para organizar un ataque.\) El comportamiento de los metadatos rige cómo y si los metadatos se ponen a disposición del mundo externo.El comportamiento de la instancia especifica cuántas instancias del servicio se pueden ejecutar \(por ejemplo, un singleton especifica solo una instancia para procesar todos los mensajes\).El comportamiento de la transacción habilita la recuperación de operaciones de transacción si se produce un error.El comportamiento de la expedición es el control de cómo la infraestructura [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] procesa un mensaje.  
  
 La extensibilidad habilita la personalización de procesos en tiempo de ejecución.Por ejemplo, la inspección del mensaje es la facilidad para inspeccionar partes de un mensaje y la filtración de parámetros permite que se realicen acciones preestablecidas basándose en filtros que actúan en encabezados del mensaje.  
  
### Mensajería  
 La capa de la mensajería se crea de *canales*.Un canal es un componente que procesa un mensaje de alguna manera, por ejemplo, autenticando un mensaje.Un conjunto de canales también se conoce como una *pila de canales*.Los canales funcionan en los mensajes y encabezados del mensaje.Esto es diferente de la capa en tiempo de ejecución del servicio, que se ocupa principalmente de procesar el contenido de los cuerpos de los mensajes.  
  
 Hay dos tipos de canales: canales de transporte y canales de protocolo.  
  
 Los canales de transporte leen y escriben mensajes de la red \(o algún otro punto de la comunicación con el mundo externo\).Algunos transportes utilizan un codificador para convertir los mensajes \(que se representan como conjuntos de información XMLs\) hacia y desde la representación de la secuencia de bytes utilizada por la red.Son ejemplos de transportes HTTP, canalizaciones con nombre, TCP y MSMQ.Son ejemplos de codificaciones XML y binario optimizado.  
  
 Los canales de protocolo implementan protocolos de procesamiento de mensajes, a menudo leyendo o escribiendo encabezados adicionales en el mensaje.Los ejemplos de tales protocolos incluyen WS\-Security y WS\-Reliability.  
  
 La capa de la mensajería muestra los posibles formatos y modelos de intercambio de los datos.WS\-Security es una implementación de la especificación WS\-Security que habilita la seguridad en la capa del mensaje.El canal de mensajería WS\-Reliable habilita la garantía de entrega del mensaje.Los codificadores presentan una variedad de codificaciones que se pueden utilizar para satisfacer las necesidades del mensaje.El canal HTTP especifica que el Protocolo de transporte de hipertexto se utiliza para la entrega del mensaje.El canal TCP especifica de manera similar el protocolo TCP.El canal de flujo de transacciones rige los modelos de mensajes de transacción.El canal de la canalización con nombre habilita la comunicación entre procesos.El canal de MSMQ habilita la interoperación con aplicaciones MSMQ.  
  
### Alojamiento y activación  
 En su forma final, un servicio es un programa.Como otros programas, un servicio se debe ejecutar en un ejecutable.Esto se conoce como un servicio *con host propio*.  
  
 Los servicios también se pueden *hospedar*o ejecutar en un ejecutable administrado por un agente externo, como IIS o Servicio de activación de Windows \(WAS\).WAS permite activar automáticamente aplicaciones [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cuando se implementan en un equipo que ejecuta WAS.Los servicios también se pueden ejecutar manualmente como ejecutables \(archivos .exe\).Un servicio también se puede ejecutar automáticamente como un servicio de Windows.Los componentes COM\+ también se pueden hospedar como servicios [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## Vea también  
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)   
 [Conceptos básicos de Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)