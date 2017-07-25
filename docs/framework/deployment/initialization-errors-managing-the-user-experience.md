---
title: "Errores de inicialización de .NET Framework: Administrar la experiencia del usuario | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- no framework found experience
- initialization errors [.NET Framework]
- .NET Framework, initialization errors
ms.assetid: 680a7382-957f-4f6e-b178-4e866004a07e
caps.latest.revision: 5
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Machine Translation
ms.sourcegitcommit: fe9ab371ab8d3eee3778412e446b7aa30b42476b
ms.openlocfilehash: 70f0515b2b4219dcb7e143b0c81f91d3855fd433
ms.contentlocale: es-es
ms.lasthandoff: 06/02/2017

---
# <a name="net-framework-initialization-errors-managing-the-user-experience"></a>Errores de inicialización de .NET Framework: Administrar la experiencia del usuario
El sistema de activación de Common Language Runtime (CLR) determina qué versión del CLR se utilizará para ejecutar código de aplicaciones administradas. El sistema de activación no siempre encuentra una versión de CLR para cargar. Esta situación normalmente se produce cuando una aplicación requiere una versión de CLR que está desusada o no está instalada en un equipo determinado. Si no se encuentra la versión solicitada, el sistema de activación de CLR devuelve un código de error HRESULT desde la función o interfaz a la que se llamó, y muestra al usuario que ejecuta la aplicación un mensaje de error. Este artículo facilita una lista de códigos HRESULT y explica cómo se puede impedir que aparezca el mensaje de error.  
  
 CLR proporciona la infraestructura de registro para ayudar a depurar los problemas de activación de CLR, tal como se describe en [How to: Debug CLR Activation Issues](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md) (Cómo: Depurar problemas de activación de CLR). Esta infraestructura no se debe confundir con los [registros de enlaces de ensamblados](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), que son completamente diferentes.  
  
## <a name="clr-activation-hresult-codes"></a>Códigos de activación HRESULT de CLR  
 Las API de activación de CLR devuelven códigos HRESULT para informar sobre el resultado de una operación de activación en un host. Los hosts de CLR deben consultar siempre estos valores devueltos antes de continuar con operaciones adicionales.  
  
-   CLR_E_SHIM_RUNTIMELOAD  
  
-   CLR_E_SHIM_RUNTIMEEXPORT  
  
-   CLR_E_SHIM_INSTALLROOT  
  
-   CLR_E_SHIM_INSTALLCOMP  
  
-   CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND  
  
-   CLR_E_SHIM_SHUTDOWNINPROGRESS  
  
## <a name="ui-for-initialization-errors"></a>Interfaz de usuario para los errores de inicialización  
 Si el sistema de activación de CLR no puede cargar la versión correcta del runtime que una aplicación requiere, entonces muestra un mensaje de error a los usuarios para informarles que el equipo no está correctamente configurado para ejecutar la aplicación y les brinda la oportunidad de solucionar el problema. El mensaje de error siguiente aparece normalmente en esta situación. El usuario puede elegir **Sí** para ir a un sitio web de Microsoft de donde puede descargar la versión correcta de .NET Framework para la aplicación.  
  
 ![Cuadro de diálogo Error de inicialización de .NET Framework](../../../docs/framework/deployment/media/initerrordialog.png "InitErrorDialog")  
Típico mensaje de error para errores de inicialización  
  
## <a name="resolving-the-initialization-error"></a>Resolución del error de inicialización  
 Como desarrollador, dispone de varias opciones para controlar el mensaje de error de inicialización de .NET Framework. Por ejemplo, puede usar una marca API para evitar que el mensaje aparezca, como se describe en la sección siguiente. Sin embargo, todavía tiene que resolver el problema que impedía que la aplicación cargara el runtime solicitado. De lo contrario, es posible que la aplicación no se ejecute en absoluto, o que alguna funcionalidad no esté disponible.  
  
 Para resolver los problemas subyacentes y proporcionarle una mejor experiencia (menos mensajes de error), se recomienda lo siguiente:  
  
-   Para las aplicaciones de .NET Framework 3.5 (y anteriores): configure la aplicación para admitir .NET Framework 4 o 4.5 (vea las [instrucciones](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)).  
  
-   Para las aplicaciones de .NET Framework 4: instale el paquete redistribuible de .NET Framework 4 como parte de la instalación de la aplicación. Vea [Deployment Guide for Developers](../../../docs/framework/deployment/deployment-guide-for-developers.md) (Guía de implementación para desarrolladores).  
  
## <a name="controlling-the-error-message"></a>Controlar el mensaje de error  
 La aparición de un mensaje de error que comunica que la versión solicitada de .NET Framework no se encontró puede considerarse tanto un servicio útil como una molestia para los usuarios. En cualquier caso, puede controlar esta interfaz de usuario pasando marcas a las API de activación.  
  
 El método [ICLRMetaHostPolicy::GetRequestedRuntime](../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) acepta un miembro de enumeración de [METAHOST_POLICY_FLAGS](../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) como entrada. Puede incluir el indicador METAHOST_POLICY_SHOW_ERROR_DIALOG para solicitar un mensaje de error si no se encuentra la versión solicitada de CLR. De forma predeterminada, el mensaje de error no se muestra. (El método [ICLRMetaHost::GetRuntime](../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) no acepta esta marca, y no facilita ninguna otra forma de mostrar el mensaje de error).  
  
 Windows proporciona una función [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkID=255242) que puede usar para manifestar si quiere que se muestren los mensajes de error como resultado del código que se ejecuta dentro del proceso. Puede especificar la marca SEM_FAILCRITICALERRORS para impedir que se muestre el mensaje de error.  
  
 Sin embargo, en algunos escenarios, es importante reemplazar el valor de SEM_FAILCRITICALERRORS establecido por un proceso de aplicación. Por ejemplo, si tiene un componente COM nativo que hospeda al CLR y que a su vez se hospeda en un proceso en el que se establece SEM_FAILCRITICALERRORS, quizás desee reemplazar la marca, teniendo en cuenta el impacto que tendrá en ese proceso de aplicación determinado el mostrar mensajes de error. En este caso, puede utilizar una de las marcas siguientes para reemplazar SEM_FAILCRITICALERRORS:  
  
-   Use METAHOST_POLICY_IGNORE_ERROR_MODE con el método [ICLRMetaHostPolicy::GetRequestedRuntime](../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md).  
  
-   Use RUNTIME_INFO_IGNORE_ERROR_MODE con la función [GetRequestedRuntimeInfo](../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md).  
  
## <a name="ui-policy-for-clr-provided-hosts"></a>Directiva de la interfaz de usuario para hosts proporcionados por CLR  
 CLR incluye un conjunto de hosts para diversos escenarios, y todos ellos muestran un mensaje de error cuando tienen problemas al cargar la versión necesaria del runtime. En la tabla siguiente se proporciona una lista de hosts y de sus directivas de mensajes de error.  
  
|Host de CLR|Descripción|Directiva de mensajes de error|¿Puede deshabilitarse el mensaje de error?|  
|--------------|-----------------|--------------------------|------------------------------------|  
|Host EXE administrado|Inicia archivos EXE administrados.|Se muestra en caso de que falte una versión de .NET Framework|No|  
|Host COM administrado|Carga los componentes COM administrados en un proceso.|Se muestra en caso de que falte una versión de .NET Framework|Sí, estableciendo la marca SEM_FAILCRITICALERRORS|  
|Host de ClickOnce|Inicia aplicaciones ClickOnce.|Se muestra en caso de que falte una versión de .NET Framework, a partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]|No|  
|Host de XBAP|Inicia aplicaciones WPF XBAP.|Se muestra en caso de que falte una versión de .NET Framework, a partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]|No|  
  
## <a name="includewin8includeswin8-mdmd-behavior-and-ui"></a>Comportamiento e interfaz de usuario de [!INCLUDE[win8](../../../includes/win8-md.md)]  
 El sistema de activación de CLR proporciona el mismo comportamiento e interfaz de usuario en [!INCLUDE[win8](../../../includes/win8-md.md)] que en otras versiones del sistema operativo Windows, excepto cuando tiene problemas el cargar CLR 2.0. [!INCLUDE[win8](../../../includes/win8-md.md)] incluye [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], que usa CLR 4.5. Sin embargo, [!INCLUDE[win8](../../../includes/win8-md.md)] no incluye .NET Framework 2.0, 3.0, o 3.5, los cuales utilizan CLR 2.0. Como resultado, las aplicaciones que dependen de CLR 2.0 no se ejecutan en [!INCLUDE[win8](../../../includes/win8-md.md)] de forma predeterminada. En su lugar, muestran el siguiente cuadro de diálogo que permite a los usuarios instalar .NET Framework 3.5. Los usuarios también pueden habilitar .NET Framework 3.5 en el Panel de control. Ambas opciones se describen en el artículo [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md) (Instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8).  
  
 ![Cuadro de diálogo para instalar 3.5 en Windows 8](../../../docs/framework/deployment/media/installdialog.png "installdialog")  
Símbolo del sistema para instalar .NET Framework 3.5 a petición  
  
> [!NOTE]
>  [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] reemplaza a .NET Framework 4 (CLR 4) en el equipo del usuario. Por consiguiente, las aplicaciones .NET Framework 4 se ejecutan perfectamente, sin mostrar este cuadro de diálogo, en [!INCLUDE[win8](../../../includes/win8-md.md)].  
  
 Cuando se instala .NET Framework 3.5, los usuarios pueden ejecutar las aplicaciones que dependen de .NET Framework 2.0, 3.0, 3.5 en sus equipos [!INCLUDE[win8](../../../includes/win8-md.md)]. También pueden ejecutar las aplicaciones de .NET Framework 1.0 y 1.1, siempre que dichas aplicaciones no estén explícitamente configuradas para ejecutarse solo en .NET Framework 1.0 o 1.1. Vea [Migración desde .NET Framework 1.1](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md).  
  
 A partir de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], el registro de activación de CLR se ha mejorado e incluye las entradas de registro que guardan cuándo y por qué aparece el mensaje de error de inicialización. Para obtener más información, vea [How to: Debug CLR Activation Issues](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md) (Cómo: Depurar problemas de activación de CLR).  
  
## <a name="see-also"></a>Vea también  
 [Guía de implementación para desarrolladores](../../../docs/framework/deployment/deployment-guide-for-developers.md)   
 [Configuración de una aplicación para admitir .NET Framework 4 o 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)   
 [Cómo: Depurar problemas de activación de CLR](../../../docs/framework/deployment/how-to-debug-clr-activation-issues.md)   
 [Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8](../../../docs/framework/install/dotnet-35-windows-10.md)
