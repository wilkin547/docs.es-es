---
title: Conceptos de seguridad empleados en WCF
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: 3ef2b9c104fa15de17a769c9ca9354e5cef085bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295554"
---
# <a name="security-concepts-used-in-wcf"></a>Conceptos de seguridad empleados en WCF
Seguridad de Windows Communication Foundation (WCF) se basa en conceptos ya está en uso e implementa en varias infraestructuras de seguridad.  
  
 WCF es compatible con algunas de esas infraestructuras, como Secure Sockets Layer (SSL) sobre HTTP (HTTPS). Sin embargo, WCF va más allá de admitir las infraestructuras de seguridad existentes implementando más nuevos estándares de seguridad interoperables (como WS-Security) a través de mensajes con codificación SOAP. Tanto si usa los mecanismos existentes como los nuevos estándares interoperables, los conceptos de seguridad subyacentes a ambos son los mismos. Entender los conceptos subyacentes de las infraestructuras existentes y los más nuevos estándares es crucial para implementar el mejor modelo de seguridad para una aplicación.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Introducción a la seguridad de los servicios Web de WCF  
 El grupo Microsoft Patterns and Practices escribió un artículo exhaustivo sobre las directrices de seguridad WCF que está disponible para su descarga aquí: [Guía de seguridad de WCF](https://go.microsoft.com/fwlink/?LinkId=210210). Estas notas sobre el producto describen los conceptos de seguridad indispensables ya que se relacionan con los servicios Web, los conceptos de seguridad clave de WCF, los escenarios de aplicaciones para redes intranet y los escenarios de aplicaciones para Internet.  
  
## <a name="industry-wide-security-specifications"></a>Especificaciones de seguridad utilizadas por la industria  
  
### <a name="public-key-infrastructure"></a>Infraestructura de clave pública (PKI)  
 La infraestructura de clave pública (PKI) es un sistema de certificados digitales, entidades de certificación y otras autoridades de registro que comprueban y autentican cada parte implicada en una transacción electrónica mediante el uso de criptografía de clave pública. Para obtener más información, consulte [servicios de certificados de Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Protocolo Kerberos  
 El *protocolo Kerberos* es una especificación para crear un mecanismo de seguridad que autentica a los usuarios en un dominio de Windows. Le permite a un usuario establecer un contexto seguro con otras entidades de un dominio. Windows 2000 y las plataformas posteriores usan el protocolo Kerberos de forma predeterminada. Entender los mecanismos del sistema es útil a la hora de crear un servicio que interactuará con clientes de la intranet. Además, dado que el *Web Services Security Kerberos Binding* está ampliamente publicado, puede usar el protocolo Kerberos para comunicarse con los clientes de Internet (es decir, el protocolo Kerberos es interoperable). Para obtener más información sobre cómo se implementa el protocolo Kerberos en Windows, consulte [Microsoft Kerberos](https://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>Certificados X.509  
 Los certificados X.509 son formularios de credenciales primarias usados en aplicaciones de seguridad. Para obtener más información sobre X.509 certificados Consulte [certificados de clave pública X.509](https://go.microsoft.com/fwlink/?LinkId=210213). Los certificados X.509 se almacenan en un almacén de certificados. Un equipo que ejecuta Windows tiene varios tipos de almacenes de certificados, cada uno con un propósito diferente. Para obtener más información sobre los diferentes almacenes, vea [almacenes de certificados](https://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Especificaciones de Seguridad de Servicios Web  
 Los enlaces definidos por el sistema admiten muchas especificaciones de seguridad de los servicios Web que se usan habitualmente. Para obtener una lista completa de los enlaces proporcionados por el sistema y las especificaciones de servicios web que admiten, vea: [Protocolos de servicios web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Mecanismos de control de acceso  
 WCF proporciona muchas formas de controlar el acceso a un servicio o a una operación. Entre ellos cabe destacar los siguientes:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. Proveedor de pertenencia a ASP.NET  
  
3. Proveedor de roles ASP.NET  
  
4. Administrador de autorización  
  
5. Modelo de identidad  
  
 Para obtener más información sobre estos temas, consulte [mecanismos de Control de acceso](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Modelo de seguridad de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
