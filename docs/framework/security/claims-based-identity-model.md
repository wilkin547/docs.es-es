---
title: Modelo de identidad basado en notificaciones
ms.date: 03/30/2017
ms.assetid: 4a96a9af-d980-43be-bf91-341a23401431
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: dadcc397783e003574d417aa6253ebc561ed28db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33398900"
---
# <a name="claims-based-identity-model"></a>Modelo de identidad basado en notificaciones
Al compilar aplicaciones para notificaciones, la identidad del usuario se representa en la aplicación como un conjunto de notificaciones. Una notificación podría ser el nombre del usuario, otra puede ser una dirección de correo electrónico. La idea es que se configure un sistema de identidad externo para proporcionar a la aplicación la información que necesita sobre el usuario con cada solicitud realizada, junto con la garantía criptográfica de que los datos de identidad recibidos proceden de una fuente de confianza.  
  
 Con este modelo, el inicio de sesión único es mucho más fácil de lograr y la aplicación ya no es responsable de las siguientes acciones:  
  
-   Autenticar usuarios.  
  
-   Almacenar cuentas de usuario y contraseñas.  
  
-   Llamar a directorios de empresa para buscar datos de identidad de usuario.  
  
-   Integrarse con sistemas de identidad de otras plataformas o empresas.  
  
 De acuerdo con este modelo, la aplicación toma decisiones relacionadas con la identidad en función de las notificaciones proporcionadas por el sistema que autenticó al usuario. Esto puede ser desde la simple personalización de la aplicación con el nombre del usuario a la autorización del usuario para obtener acceso a características y recursos de más valor en la aplicación.  
  
 En este tema se proporciona la información siguiente:  
  
-   [Introducción a la identidad basada en notificaciones](../../../docs/framework/security/claims-based-identity-model.md#BKMK_1)  
  
-   [Escenario básico para un modelo de identidad basado en notificaciones](../../../docs/framework/security/claims-based-identity-model.md#BKMK_2)  
  
<a name="BKMK_1"></a>   
## <a name="introduction-to-claims-based-identity"></a>Introducción a la identidad basada en notificaciones  
 La terminología y los conceptos siguientes pueden ayudar a entender esta nueva arquitectura de identidad.  
  
### <a name="identity"></a>identidad  
 En las descripciones del modelo de programación de Windows Identity Foundation (WIF), se usa el término "identidad" para representar un conjunto de atributos que describen a un usuario o a alguna otra entidad de un sistema que se quiere proteger.  
  
### <a name="claim"></a>Notificación  
 Piense en una notificación como un fragmento de información de identidad como nombre, dirección de correo electrónico, edad, la pertenencia al rol de ventas. Cuantas más notificaciones reciba la aplicación, más información se tendrá del usuario. Puede que se pregunte por qué se les denomina "notificaciones" en lugar de "atributos", que es el término que se usa habitualmente para describir directorios de empresa. El motivo está relacionado con el método de entrega. En este modelo, la aplicación no busca atributos de usuario en un directorio. En su lugar, el usuario envía notificaciones a la aplicación que, a su vez, las examina. Cada notificación la realiza un emisor y se confía en la notificación en la misma medida en que se confía en el emisor. Por ejemplo, se confía más en una notificación realizada por el controlador de dominio de su empresa que en otra realizada por el propio usuario. WIF representa las notificaciones con un tipo <xref:System.Security.Claims.Claim>, que tiene una propiedad <xref:System.Security.Claims.Claim.Issuer%2A> que permite averiguar quién emitió la notificación.  
  
### <a name="security-token"></a>Token de seguridad  
 El usuario envía un conjunto de notificaciones a la aplicación junto con una solicitud. En un servicio Web, estas notificaciones se incluyen en el encabezado de seguridad de la envoltura SOAP. En una aplicación web basada en el explorador, las notificaciones llegan a través de HTTP POST desde el explorador del usuario y pueden almacenarse en caché posteriormente en una cookie para sesiones futuras. Independientemente de cómo lleguen las notificaciones, estas deben serializarse y para ello se usan los tokens de seguridad. Un token de seguridad es un conjunto serializado de notificaciones firmadas digitalmente por la autoridad emisora. La signatura es importante: garantiza que el usuario no se limitó a realizar una serie de notificaciones y enviarlas. En situaciones de escasa seguridad donde la criptografía no es necesaria o no se desea aplicarla, pueden usarse tokens sin firma, pero ese escenario no se describe en este tema.  
  
 Una de las características básicas de WIF es la capacidad de crear y leer tokens de seguridad. WIF y .NET Framework controlan todo el trabajo criptográfico y presentan la aplicación con un conjunto de notificaciones que se pueden leer.  
  
### <a name="issuing-authority"></a>Entidad emisora  
 Hay muchos tipos diferentes de entidades emisoras, desde controladores de dominio que emiten vales Kerberos a entidades de certificación que emiten certificados X.509, pero el tipo concreto de entidad que se trata en este tema emite tokens de seguridad que contienen notificaciones. Esta entidad emisora es una aplicación web o un servicio Web que sabe cómo emitir tokens de seguridad. Debe tener suficiente información para poder emitir las notificaciones adecuadas de acuerdo con el usuario de confianza de destino y el usuario que realiza la solicitud. Además, puede que tenga que interactuar con almacenes de usuario para buscar notificaciones y autenticar a los propios usuarios.  
  
 Independientemente de la entidad emisora elegida, esta tiene un papel fundamental en la solución de identidad. Cuando se factoriza la autenticación fuera de la aplicación basándose en las notificaciones, se cede la responsabilidad a dicha entidad y se le pide que autentique a los usuarios en su nombre.  
  
### <a name="security-token-service-sts"></a>Servicio de tokens de seguridad (STS)  
 Un servicio de token de seguridad (STS) es el componente de servicio que compila, firma y emite tokens de seguridad según los protocolos WS-Trust y WS-Federation. Se invierte mucho trabajo en la implementación de estos protocolos, pero WIF lo realiza automáticamente, lo que permite que un usuario sin experiencia en los protocolos ponga en marcha un STS sin apenas esfuerzo. Se puede usar un STS precompilado como [Servicios de federación de Active Directory® (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516), un STS en la nube como [Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) o, si quiere emitir tokens personalizados o proporcionar autenticación o autorización personalizadas, puede compilar su propio STS personalizado mediante WIF. WIF facilita la compilación de su propio STS.  
  
### <a name="relying-party-application"></a>Aplicación de usuario de confianza  
 Cuando se compila una aplicación basada en las notificaciones, se está compilando una aplicación de usuario de confianza (RP). Entre los sinónimos de RP se incluyen "aplicación para notificaciones" y "aplicación basada en notificaciones". Tanto las aplicaciones web como los servicios Web pueden ser de este tipo. Una aplicación de usuario de confianza usa los tokens emitidos por un STS y extrae las notificaciones de los tokens para usarlas en tareas relacionadas con la identidad. WIF ofrece funcionalidades para ayudar a compilar aplicaciones de usuario de confianza.  
  
### <a name="standards"></a>Estándares  
 Para que haya interoperabilidad, en el escenario anterior se usan varios estándares WS-*. La directiva se recupera usando WS-MetadataExchange, mientras que la propia directiva se estructura según la especificación WS-Policy. El STS expone los puntos de conexión que implementan la especificación WS-Trust, que describe cómo solicitar y recibir tokens de seguridad. En la actualidad, la mayoría de los STS emiten tokens con lenguaje de marcado de aserción de seguridad (SAML) como formato. El lenguaje SAML es un vocabulario XML reconocido del sector que se puede usar para representar las notificaciones de forma interoperable. Asimismo, en una situación multiplataforma, este permite comunicarse con un STS o una plataforma completamente distinta y lograr un inicio de sesión único en todas las aplicaciones, independientemente de la plataforma.  
  
### <a name="browser-based-applications"></a>Aplicaciones basadas en el explorador  
 Los clientes inteligentes no son los únicos que pueden usar el modelo de identidad basado en notificaciones. Las aplicaciones basadas en el explorador (también conocidas como clientes pasivos) también pueden usarlo. En el escenario siguiente se describe su funcionamiento.  
  
 En primer lugar, el usuario señala a un explorador en una aplicación web para notificaciones (la aplicación de usuario de confianza). La aplicación web redirige al explorador al STS de modo que el usuario pueda autenticarse. El STS se hospeda en una aplicación web simple que lee la solicitud entrante, autentica al usuario mediante mecanismos HTTP estándar y, a continuación, crea un token de SAML y responde con un fragmento de código JavaScript que hace que el explorador inicie un método HTTP POST, que vuelve a enviar el token de SAML a la aplicación de usuario de confianza. El cuerpo de este POST contiene las notificaciones solicitadas por la aplicación de usuario de confianza. En este punto, la aplicación de usuario de confianza suele empaquetar las notificaciones en una cookie de modo que no haya que redirigir al usuario para cada solicitud.  
  
<a name="BKMK_2"></a>   
## <a name="basic-scenario-for-a-claims-based-identity-model"></a>Escenario básico para un modelo de identidad basado en notificaciones  
 A continuación se muestra un ejemplo de sistema basado en notificaciones.  
  
 ![Recurrir al flujo de autenticación de partner](../../../docs/framework/security/media/conc-relying-partner-processc.png "conc_relying_partner_processc")  
  
 En este diagrama se muestra un sitio web (la aplicación de usuario de confianza, RP) que se ha configurado para usar WIF para la autenticación y un cliente, un explorador web, que desea usar ese sitio.  
  
1.  Cada vez que un usuario no autenticado solicita una página, el explorador se redirige a las páginas del proveedor de identidad (IP).  
  
2.  Dicho proveedor solicita al usuario que presente sus credenciales, por ejemplo, nombre de usuario/contraseña, Kerberos, etc.  
  
3.  El IP vuelve a emitir un token que se devuelve al explorador.  
  
4.  A continuación, el explorador se redirige a la página solicitada originalmente, donde WIF determina si el token cumple los requisitos para tener acceso a la misma. En ese caso, se emite una cookie para establecer una sesión de modo que la autenticación solo tenga que realizarse una vez y el control se pase a la aplicación.
