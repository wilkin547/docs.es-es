---
title: Conceptos de seguridad empleados en WCF
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: faf7b44c0ff1b207a7b017163ad2b032f26199b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743884"
---
# <a name="security-concepts-used-in-wcf"></a>Conceptos de seguridad empleados en WCF
La seguridad de Windows Communication Foundation (WCF) se basa en los conceptos que ya están en uso y se implementan en diversas infraestructuras de seguridad.  
  
 WCF admite algunas de esas infraestructuras, como Capa de sockets seguros (SSL) sobre HTTP (HTTPS). Sin embargo, WCF va más allá de la compatibilidad con infraestructuras de seguridad existentes mediante la implementación de estándares de seguridad interoperables más recientes (como WS-Security) en mensajes codificados con SOAP. Tanto si usa los mecanismos existentes como los nuevos estándares interoperables, los conceptos de seguridad subyacentes a ambos son los mismos. Entender los conceptos subyacentes de las infraestructuras existentes y los más nuevos estándares es crucial para implementar el mejor modelo de seguridad para una aplicación.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Introducción a la seguridad de los servicios Web de WCF  

El grupo Microsoft Patterns and Practices escribió una nota del producto detallada denominada [Guía de seguridad de WCF](https://archive.codeplex.com/?p=wcfsecurityguide). En estas notas del producto se describen los conceptos fundamentales de seguridad relacionados con los servicios Web, los conceptos clave de seguridad de WCF, los escenarios de aplicaciones de intranet y los escenarios de aplicaciones de Internet.  
  
## <a name="industry-wide-security-specifications"></a>Especificaciones de seguridad utilizadas por la industria  
  
### <a name="public-key-infrastructure"></a>Infraestructura de clave pública (PKI)  

La infraestructura de clave pública (PKI) es un sistema de certificados digitales, entidades de certificación y otras autoridades de registro que comprueban y autentican cada parte implicada en una transacción electrónica mediante el uso de criptografía de clave pública.
  
### <a name="kerberos-protocol"></a>Protocolo Kerberos  
 El *protocolo Kerberos* es una especificación para crear un mecanismo de seguridad que autentica a los usuarios en un dominio de Windows. Le permite a un usuario establecer un contexto seguro con otras entidades de un dominio. Windows 2000 y las plataformas posteriores usan el protocolo Kerberos de forma predeterminada. Entender los mecanismos del sistema es útil a la hora de crear un servicio que interactuará con clientes de la intranet. Además, puesto que el *enlace de kerberos seguridad de servicios web* está ampliamente publicado, puede usar el protocolo Kerberos para comunicarse con clientes de Internet (es decir, el protocolo Kerberos es interoperable). Para obtener más información sobre cómo se implementa el protocolo Kerberos en Windows, vea [Microsoft Kerberos](/windows/win32/secauthn/microsoft-kerberos).  
  
### <a name="x509-certificates"></a>Certificados X.509  
 Los certificados X.509 son formularios de credenciales primarias usados en aplicaciones de seguridad. Para obtener más información sobre los certificados X. 509, vea [certificados de clave pública x. 509](/windows/win32/seccertenroll/about-x-509-public-key-certificates). Los certificados X.509 se almacenan en un almacén de certificados. Un equipo que ejecuta Windows tiene varios tipos de almacenes de certificados, cada uno con un propósito diferente. Para obtener más información sobre los diferentes almacenes, vea [almacenes de certificados](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
## <a name="web-services-security-specifications"></a>Especificaciones de Seguridad de Servicios Web  
 Los enlaces definidos por el sistema admiten muchas especificaciones de seguridad de los servicios Web que se usan habitualmente. Para obtener una lista completa de los enlaces proporcionados por el sistema y las especificaciones de los servicios web que admiten, vea: [protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md) .  
  
## <a name="access-control-mechanisms"></a>Mecanismos de control de acceso  
 WCF proporciona muchas formas de controlar el acceso a un servicio o a una operación. Entre ellos cabe destacar los siguientes:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. Proveedor de pertenencia a ASP.NET  
  
3. Proveedor de roles ASP.NET  
  
4. Administrador de autorización  
  
5. Modelo de identidad  
  
 Para obtener más información sobre estos temas, vea [mecanismos de Access Control](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
