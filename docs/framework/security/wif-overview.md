---
title: Información general de Windows Identity Foundation 4.5
ms.date: 03/30/2017
ms.assetid: 5f723345-7270-49e2-b638-b3a34bd40517
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6cfe09e7df28d6f36f6e606802597449dab38212
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399989"
---
# <a name="windows-identity-foundation-45-overview"></a>Información general de Windows Identity Foundation 4.5
Windows Identity Foundation 4.5 es un conjunto de clases de .NET Framework para implementar la identidad basada en notificaciones en las aplicaciones. Al usarlo, se beneficiará fácilmente de las ventajas de las aplicaciones y los servicios compatibles con notificaciones. WIF 4.5 se puede usar en cualquier aplicación web o servicio Web que use .NET Framework versión 4.5 o versiones posteriores. WIF es solo una parte de la familia de software de identidad federada de Microsoft que implementa la visión compartida del sector basada en estándares abiertos. La identidad federada consta de tres componentes: [Servicios de federación de Active Directory®](https://go.microsoft.com/fwlink/?LinkID=247516) (AD FS) 2.0, [Windows Azure Access Control Services](https://go.microsoft.com/fwlink/?LinkID=247517) (ACS) y WIF. Juntos, estos tres componentes forman el núcleo de la nueva plataforma de acceso e identidad de nube basada en notificaciones de Microsoft.  
  
 Para obtener más información sobre WIF, vea el [sitio Web de Windows Identity Foundation](https://go.microsoft.com/fwlink/?LinkId=149009) en el centro de seguridad para desarrolladores en MSDN. Para obtener una introducción a la creación de aplicaciones con WIF, consulte [Programming Windows Identity Foundation](https://go.microsoft.com/fwlink/?LinkId=210158) de Vittorio Bertocci (publicado por Microsoft Press).  
  
## <a name="wif-45-features"></a>Características de WIF 4.5  
 WIF 4.5 es un marco de trabajo para la compilación de aplicaciones que incluyen identidad. El marco de trabajo extrae los protocolos WS-Trust y WS-Federation y presenta a los desarrolladores las API para compilar tanto aplicaciones compatibles con notificaciones como servicios de token de seguridad (STS), en caso necesario. Las aplicaciones pueden usar WIF para procesar los tokens emitidos desde los STS, como AD FS 2.0 y ACS, así como tomar decisiones basadas en la identidad en la aplicación web o el servicio Web.  
  
 WIF 4.5 tiene las siguientes características principales:  
  
-   Compilación de aplicaciones para notificaciones (aplicaciones de usuario de confianza). WIF ayuda a los desarrolladores a compilar aplicaciones para notificaciones. Además de proporcionar un modelo de notificaciones, facilita a los desarrolladores de aplicaciones un conjunto completo de API para ayudar a tomar decisiones relativas al acceso de los usuarios basadas en notificaciones.  Asimismo, WIF ofrece a los desarrolladores una experiencia de programación uniforme en caso de que decidan compilar sus aplicaciones en entornos ASP.NET o de WCF.  
  
-   Compilación de compatibilidad con delegación de identidad en aplicaciones para notificaciones.  WIF ofrece la capacidad de mantener las identidades de los solicitantes originales a través de los diversos límites de servicio. Esta capacidad se puede lograr mediante la funcionalidad "ActAs" u "OnBehalfOf" en el marco de trabajo y ofrece a los desarrolladores la capacidad de agregar compatibilidad con la delegación de identidad en las aplicaciones para notificaciones.  
  
-   Compilación de STS personalizados.  WIF facilita enormemente la compilación de un STS personalizado que admita el protocolo WS-Trust. Este tipo de STS también se conoce como STS activo.  
  
     Además, el marco de trabajo también ofrece compatibilidad para compilar un STS que admita WS-Federation para permitir clientes del explorador web. Este tipo de STS también se conoce como STS pasivo.  
  
-   La nueva herramienta Identity and Access Tool de Visual Studio 11 que permite proteger la aplicación mediante la identidad basada en notificaciones y aceptar usuarios de diversos proveedores de identidad. Esta herramienta WIF se puede descargar desde la siguiente dirección URL: [ https://go.microsoft.com/fwlink/?LinkID=245849 ](https://go.microsoft.com/fwlink/?LinkID=245849) o directamente desde Visual Studio 11 buscando "identity" en el Administrador de extensiones. Para más información, vea [Identity and Access Tool for Visual Studio 2012 (Herramienta de identidad y acceso para Visual Studio 2012)](../../../docs/framework/security/identity-and-access-tool-for-vs.md).  
  
 WIF admite los siguientes escenarios principales:  
  
-   Federación.  WIF permite habilitar la federación entre dos o más partners. Al ofrecer compatibilidad con la compilación de aplicaciones para notificaciones y STS personalizados, ayuda a los desarrolladores a lograr este escenario.  
  
-   Delegación de identidad.  WIF facilita el mantenimiento de las identidades a través de los límites de servicio de modo que los desarrolladores puedan lograr un escenario de delegación de identidad.  
  
-   Autenticación superior. Los requisitos de autenticación para los distintos recursos dentro de una aplicación pueden variar. WIF ofrece a los desarrolladores la capacidad de compilar aplicaciones que pueden requerir requisitos de autenticación incrementales (por ejemplo: inicio de sesión inicial con autenticación mediante nombre de usuario/contraseña y después autenticación mediante tarjeta inteligente).  
  
 Al usar WIF, se beneficiará fácilmente de las ventajas del modelo de identidad basado en notificaciones. Para más información, vea [Windows Identity Foundation White Paper for Developers (Notas del producto para desarrolladores de Windows Identity Foundation)](https://download.microsoft.com/download/7/d/0/7d0b5166-6a8a-418a-addd-95ee9b046994/windowsidentityfoundationwhitepaperfordevelopers-rtw.pdf).
