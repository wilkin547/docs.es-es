---
title: "Protocolo de resoluci&#243;n de nombres del mismo nivel | Microsoft Docs"
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
ms.assetid: 11940511-c124-4d91-ae31-d4ed6e81ee58
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Protocolo de resoluci&#243;n de nombres del mismo nivel
En entornos entre iguales, los pares utilizan los sistemas de resolución de nombres específicos para resolver las ubicaciones de red de cada \(direcciones, protocolos, y puertos\) de nombres u otros tipos de identificadores.  En el pasado, la resolución de nombres de mismo nivel ha sido complicado por la conectividad inherentemente transitorio junto con otros defectos dentro de Domain Name System \(DNS\).  
  
 La plataforma entre iguales de red de Microsoft® Windows® resuelve este problema con Peer Name Resolution Protocol \(PNRP\), un registro de nombre y un protocolo seguros, escalables, y dinámicos de la resolución de nombres primero desarrollado para Windows XP y luego actualizado en ™ de Windows Vista.  PNRP funciona muy de manera diferente de los sistemas de resolución de nombres tradicionales, abrir nuevas posibilidades emocionantes de desarrolladores de aplicaciones.  
  
 Con PNRP, los nombres del mismo nivel se pueden aplicar al equipo, o aplicaciones concretas o los servicios del equipo.  Una resolución de nombres de mismo nivel incluye una dirección, el puerto, y posiblemente una carga extendida.  Ventajas de esta tolerancia a errores de inclusión del sistema, de cualquier cuellos de botella, y de las soluciones de nombres que nunca devolverán direcciones obsoleto; crear el protocolo una solución excelente para localizar a usuarios móviles.  
  
 En términos de seguridad, los nombres del mismo nivel se pueden publicar como asegúrese de \(protected\) o no seguro \(desprotegido\).  PNRP utiliza criptografía de clave pública para proteger nombres del mismo nivel seguros contra la suplantación; los equipos y los servicios se pueden llamar a PNRP.  
  
-   Peer Name Resolution Protocol muestra las propiedades siguientes:  
  
-   Enrutado y casi por serverless.  Requieren únicamente los Servidores para el proceso de arranque.  
  
-   Publicación segura de nombre sin implicación de terceros.  A diferencia de publicación de nombre DNS, la publicación de nombre de PNRP es instantánea y sin costo financiero.  
  
-   Actualizaciones de PNRP en tiempo real, que impide la resolución de direcciones obsoleto.  
  
-   La resolución de nombres mediante PNRP se extiende más allá de los equipos también permite la resolución de nombres para los servicios.  
  
## El espacio de nombres System.Net.PeerToPeer  
  
-   La funcionalidad de PNRP es definida por el espacio de nombres <xref:System.Net.PeerToPeer> dentro de la versión 3,5 de .NET Framework.  Proporciona un conjunto de tipos que se pueden utilizar para registrar y resolver nombres del mismo nivel con un servicio disponible de PNRP.  
  
-   \(PNRP y los resoluciones de espacios de nombres de mismo nivel de personalizadas se pueden crear y crear instancias utilizando los tipos proporcionados en el espacio de nombres <xref:System.ServiceModel.PeerResolvers> .\)  
  
-   Los tipos básicos utilizados para registrar y los nombres de resolución con un servicio disponible de PNRP son los siguientes:  
  
-   <xref:System.Net.PeerToPeer.Cloud>: Define la información que describe una nube disponibles de PNRP, incluida su ámbito.  
  
-   <xref:System.Net.PeerToPeer.PeerName>: Define un nombre del mismo nivel que se puede utilizar para registrar y resolver posteriormente a un par de una nube.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRecord>: Define el registro en la nube de PNRP que contiene información de registro para un par, que incluye los extremos de la red en los que el par puede poner.  
  
-   <xref:System.Net.PeerToPeer.PeerNameRegistration>: Define el proceso de registro para un nombre del mismo nivel, incluidos los métodos para iniciar y detener el registro del mismo nivel de nombre.  
  
-   <xref:System.Net.PeerToPeer.PeerNameResolver>: Define el proceso para resolver un nombre del mismo nivel al final de la red, incluidos sincrónico y métodos asincrónicos para la resolución.  
  
## Vea también  
 <xref:System.ServiceModel.PeerResolvers>   
 <xref:System.Net.PeerToPeer>   
 [Ejemplos de programación de red](../../../docs/framework/network-programming/network-programming-samples.md)   
 [ejemplo de tecnología PeerToPeer](http://go.microsoft.com/fwlink/?LinkID=179571)