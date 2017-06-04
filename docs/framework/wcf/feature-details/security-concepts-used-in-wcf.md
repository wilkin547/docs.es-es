---
title: "Conceptos de seguridad empleados en WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# Conceptos de seguridad empleados en WCF
La seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se basa en conceptos ya en uso e implementados en varias infraestructuras de seguridad.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite algunas de esas infraestructuras, como Secure Sockets Layer \(SSL\) sobre HTTP \(HTTPS\).Sin embargo, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] va más allá de admitir las infraestructuras de seguridad existentes implementando las más nuevas normas de seguridad interoperables \(como WS\-Security\) en mensajes codificados por SOAP.Tanto si usa los mecanismos existentes como los nuevos estándares interoperables, los conceptos de seguridad subyacentes a ambos son los mismos.Entender los conceptos subyacentes de las infraestructuras existentes y los más nuevos estándares es crucial para implementar el mejor modelo de seguridad para una aplicación.  
  
## Introducción a la seguridad de los servicios Web de WCF  
 El grupo Microsoft Patterns and Practices escribió unas notas del producto muy completas sobre información orientativa de seguridad de WCF que están disponibles para su descarga aquí: [Guía de seguridad de WCF](http://go.microsoft.com/fwlink/?LinkId=210210).Estas notas sobre el producto describen los conceptos de seguridad indispensables ya que se relacionan con los servicios Web, los conceptos de seguridad clave de WCF, los escenarios de aplicaciones para redes intranet y los escenarios de aplicaciones para Internet.  
  
## Especificaciones de seguridad utilizadas por la industria  
  
### Infraestructura de clave pública \(PKI\)  
 La infraestructura de clave pública \(PKI\) es un sistema de certificados digitales, entidades de certificación y otras autoridades de registro que comprueban y autentican cada parte implicada en una transacción electrónica mediante el uso de criptografía de clave pública.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Servicios de servidor de certificados de Windows Server 2008 R2](http://go.microsoft.com/fwlink/?LinkId=210211).  
  
### Protocolo Kerberos  
 El *protocolo Kerberos* es una especificación para crear un mecanismo de seguridad que autentique a los usuarios en un dominio de Windows.Le permite a un usuario establecer un contexto seguro con otras entidades de un dominio.Windows 2000 y las plataformas posteriores usan el protocolo Kerberos de forma predeterminada.Entender los mecanismos del sistema es útil a la hora de crear un servicio que interactuará con clientes de la intranet.Además, dado que el *enlace Kerberos de seguridad de servicios web* se publica ampliamente, puede usar el protocolo Kerberos para comunicarse con clientes de Internet \(es decir, el protocolo Kerberos es interoperable\).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo se implementa el protocolo Kerberos en Windows, vea [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).  
  
### Certificados X.509  
 Los certificados X.509 son formularios de credenciales primarias usados en aplicaciones de seguridad.Para obtener más información sobre los certificados X.509, vea [Certificados X.509 de clave pública](http://go.microsoft.com/fwlink/?LinkId=210213).Los certificados X.509 se almacenan en un almacén de certificados.Un equipo que ejecuta Windows tiene varios tipos de almacenes de certificados, cada uno con un propósito diferente.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] los diferentes almacenes, vea [Almacenes de certificados](http://go.microsoft.com/fwlink/?LinkID=87787).  
  
## Especificaciones de Seguridad de Servicios Web  
 Los enlaces definidos por el sistema admiten muchas especificaciones de seguridad de los servicios Web que se usan habitualmente.Para obtener una lista completa de los enlaces proporcionados por el sistema y de las especificaciones de los servicios Web que admiten, vea: [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## Mecanismos de control de acceso  
 WCF proporciona muchas formas de controlar el acceso a un servicio o a una operación.Entre ellos cabe destacar los siguientes:  
  
1.  <xref:System.Security.Permissions.PrinciplePermissionAttribute>  
  
2.  Proveedor de pertenencia a ASP.NET  
  
3.  Proveedor de roles ASP.NET  
  
4.  Administrador de autorización  
  
5.  Modelo de identidad  
  
 Para obtener más información sobre estos temas, vea [Mecanismos de control de acceso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md).  
  
## Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Modelo de seguridad para Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)