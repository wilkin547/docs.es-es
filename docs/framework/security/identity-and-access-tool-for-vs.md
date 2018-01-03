---
title: Identity and Access Tool para Visual Studio 2012
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 079c3798f17f4929124cd5cb027baa5d40a1167a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a>Identity and Access Tool para Visual Studio 2012
En este tema se describe la nueva Identity and Access Tool para Visual Studio 11. Esta herramienta se puede descargar en la dirección URL siguiente: [http://go.microsoft.com/fwlink/?LinkID=245849](http://go.microsoft.com/fwlink/?LinkID=245849) o directamente desde Visual Studio 11, buscando "identity" en el Administrador de extensiones.  
  
 Identity and Access Tool para Visual Studio 11 ofrece una experiencia en tiempo de desarrollo considerablemente simplificada en la que destacan los siguientes aspectos:  
  
-   Al usar la nueva herramienta, se puede desarrollar mediante tipos de proyecto de aplicaciones web y tener IIS Express como destino.  
  
-   A diferencia de la autenticación abierta de solo protección, con la nueva herramienta se puede especificar el controlador o la página de detección de dominios de inicio locales (o cualquier otro punto de conexión que controle la experiencia de autenticación en la aplicación) y WIF configurará todas las solicitudes no autenticadas para dirigirse a estos, en lugar de redirigirlas al STS.  
  
-   La herramienta incluye un servicio de token de seguridad (STS) de prueba que se ejecuta en el equipo local al iniciar una sesión de depuración. Por consiguiente, ya no es necesario crear proyectos de STS personalizados ni ajustarlos para obtener las notificaciones requeridas para probar las aplicaciones. Los tipos y valores de notificación son totalmente personalizables.  
  
-   La configuración general puede modificarse directamente a través de la interfaz de usuario de la herramienta, sin necesidad de editar el archivo web.config.  
  
-   Se puede establecer la federación con los Servicios de federación de Active Directory (AD FS) 2.0 (u otros proveedores de WS-Federation) en una única pantalla.  
  
-   La herramienta aprovecha las capacidades del Servicio de control de acceso (ACS) de Microsoft Azure con una simple lista de casillas para todos los proveedores de identidad que desea usar: Facebook, Google, Live ID, Yahoo!, los proveedores de OpenID y los de WS-Federation. Seleccione los proveedores de identidad, haga clic en Aceptar y, a continuación, presione F5. Tanto la aplicación como ACS se configurarán automáticamente y la aplicación de prueba será compatible con ACS.  
  
## <a name="see-also"></a>Vea también  
 [Características de WIF](../../../docs/framework/security/wif-features.md)
