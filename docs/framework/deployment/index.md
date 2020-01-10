---
title: Implementar .NET Framework y aplicaciones
ms.date: 03/30/2017
helpviewer_keywords:
- deploying applications [.NET Framework], packaging
- deploying applications [.NET Framework]
- deploying applications [.NET Framework], features
- deploying applications [.NET Framework], distribution
- .NET Framework, deploying
- .NET Framework application deployment
ms.assetid: 238d8284-6042-4a38-a7f6-1ee8efd719da
ms.openlocfilehash: b1ba9810b4b0d5a1688318db1093a9ce9bdf8fda
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716461"
---
# <a name="deploying-the-net-framework-and-applications"></a>Implementar .NET Framework y aplicaciones

Este artículo le ayuda a empezar a implementar .NET Framework con la aplicación. La mayoría de la información está destinada a desarrolladores, OEM y administradores de empresa. Los usuarios que deseen instalar .NET Framework en sus equipos deben leer [Instalar .NET Framework](../install/index.md).

## <a name="key-deployment-resources"></a>Recursos de implementación clave

Use los siguientes vínculos a otros temas de MSDN para obtener información específica sobre la implementación y mantenimiento de .NET Framework.

**Instalación e implementación**

- Información general para el instalador y la implementación:

  - Opciones del instalador:

    - [Instalador web](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

    - [Instalador sin conexión](../install/guide-for-developers.md#to-install-or-download-the-net-framework-redistributable)

  - Modos de instalación:

    - [Instalación silenciosa](deployment-guide-for-developers.md#chaining_custom)

    - [Mostrar una interfaz de usuario](deployment-guide-for-developers.md#chaining_default)

  - [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](reducing-system-restarts.md)

  - [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)

- Implementar .NET Framework con una aplicación cliente (para desarrolladores):

  - [Usar InstallShield](deployment-guide-for-developers.md#installshield-deployment) en un proyecto de instalación e implementación

  - [Usar una aplicación ClickOnce de Visual Studio](deployment-guide-for-developers.md#clickonce-deployment)

  - [Crear un paquete de instalación de WiX](deployment-guide-for-developers.md#wix)

  - [Usar un instalador personalizado](deployment-guide-for-developers.md#chaining)

  - [Información adicional](deployment-guide-for-developers.md) para desarrolladores

- Implementar .NET Framework (para OEM y administradores):

  - [Windows Assessment and Deployment Kit (ADK)](https://go.microsoft.com/fwlink/p/?LinkId=254976)

  - [Guía del administrador](guide-for-administrators.md)

**Mantenimiento**

- Para obtener información general, vea el [blog de .NET Framework](https://devblogs.microsoft.com/dotnet/).

- [Detectar versiones](../migration-guide/how-to-determine-which-versions-are-installed.md)

- [Detectar Service Pack y actualizaciones](../migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)

## <a name="features-that-simplify-deployment"></a>Características que simplifican la implementación

.NET Framework proporciona algunas características básicas que facilitan la implementación de las aplicaciones:

- Aplicaciones carentes de impacto.

     Esta característica permite aislar la aplicación y eliminar conflictos de archivos DLL. De forma predeterminada, los componentes no afectan a otras aplicaciones

- Componentes privados predeterminados.

     De forma predeterminada, los componentes se implementan en el directorio de la aplicación y sólo son visibles para la aplicación en la que están incluidos.

- Uso compartido de código controlado.

     El uso compartido de código no es el comportamiento predeterminado; para compartir código, es necesario que este quede explícitamente disponible para el uso compartido.

- Control de versiones en paralelo.

     Es posible que coexistan varias versiones de un componente o de una aplicación; el usuario puede elegir las versiones que desea utilizar, y Common Language Runtime impone la directiva de control de versiones.

- Implementación y duplicación mediante XCOPY.

     Los componentes y aplicaciones autodescriptivos e independientes pueden implementarse sin entradas del Registro o dependencias.

- Actualizaciones inmediatas.

     Los administradores pueden utilizar servidores host, como ASP.NET, para actualizar programas de archivos DLL, incluso en equipos remotos.

- Integración con Windows Installer.

     A la hora de implementar la aplicación, estarán disponibles las características de anuncio, edición, reparación e instalación a petición.

- Implementación de empresa.

     Esta característica proporciona una distribución de software sencilla, que incluye el uso de Active Directory.

- Descarga y almacenamiento en caché.

     Las descargas incrementales reducen el tamaño de las mismas, y los componentes pueden aislarse a fin de que solo los use la aplicación para una implementación de bajo impacto.

- Código que no es de plena confianza.

     La identidad no se basa en el usuario sino en el código y no aparece ningún cuadro de diálogo de certificado.

## <a name="packaging-and-distributing-net-framework-applications"></a>Empaquetar y distribuir aplicaciones de .NET Framework

Parte de la información relacionada con el empaquetado y la implementación de .NET Framework se describe en otras secciones de la documentación. En esas secciones se proporciona información sobre los [ensamblados](../../standard/assembly/index.md), que son unidades autodescriptivas que no necesitan entradas del Registro, los [ensamblados con nombre seguro](../../standard/assembly/strong-named.md), que garantizan el carácter unívoco del nombre e impiden la simulación de este, y el [control de versiones de los ensamblados](../../standard/assembly/versioning.md), que aborda muchos de los problemas asociados a conflictos de archivos DLL. En las siguientes secciones, se proporciona información sobre cómo se empaquetan y se distribuyen las aplicaciones de .NET Framework.

### <a name="packaging"></a>Empaquetado

.NET Framework proporciona las siguientes opciones para empaquetar aplicaciones:

- Como un solo ensamblado o como una colección de ensamblados.

     Con esta opción, simplemente se emplean los archivos.dll o .exe tal y como se compilaron.

- Como archivos contenedores (CAB).

     Con esta opción, los archivos se comprimen en archivos .cab para disminuir el tiempo de distribución y descarga.

- Como un paquete de Microsoft Windows Installer o en otros formatos de instalación.

     Con esta opción, se crean archivos .msi para usarlos con Windows Installer o se empaqueta la aplicación para utilizarla con otro instalador.

### <a name="distribution"></a>Distribución

.NET Framework proporciona las siguientes opciones para distribuir aplicaciones:

- Utilizar XCOPY o FTP.

     Como las aplicaciones de tipo Common Language Runtime son autodescriptivas y no precisan entradas del Registro, se puede utilizar XCOPY o FTP simplemente para copiar la aplicación en un directorio adecuado. La aplicación puede entonces ejecutarse desde ese directorio.

- Emplear descarga de código.

     Si la aplicación se está distribuyendo a través de Internet o de una intranet corporativa, puede simplemente descargar el código en un equipo y ejecutar la aplicación allí mismo.

- Utilizar un programa de instalación como Windows Installer 2.0.

     Windows Installer 2.0 puede instalar, reparar o quitar ensamblados de .NET Framework de la memoria caché global de ensamblados y de directorios privados.

### <a name="installation-location"></a>Ubicación de instalación

Para determinar la ubicación donde se van a implementar los ensamblados de la aplicación para que el runtime los encuentre, vea [Cómo el motor en tiempo de ejecución ubica ensamblados](how-the-runtime-locates-assemblies.md).

Las cuestiones de seguridad pueden afectar también al modo en que se implementa la aplicación. Los permisos de seguridad se conceden al código administrado según la ubicación del código. Si se implementa una aplicación o un componente en una ubicación donde reciba poca confianza, como Internet, se verán limitadas las funciones de dicha aplicación o dicho componente. Para obtener más información sobre la implementación y la seguridad, vea [Conceptos básicos sobre la seguridad de acceso del código](../misc/code-access-security-basics.md).

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Cómo el motor en tiempo de ejecución ubica ensamblados](how-the-runtime-locates-assemblies.md)|Describe la forma en que Common Language Runtime determina el ensamblado que se va a utilizar para llevar a cabo una solicitud de enlace.|
|[Procedimientos recomendados para cargar ensamblados](best-practices-for-assembly-loading.md)|Aborda formas de evitar problemas de identidad de tipos que pueden causar errores como <xref:System.InvalidCastException> o <xref:System.MissingMethodException>, entre otros.|
|[Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](reducing-system-restarts.md)|Describe el Administrador de reinicio, que evita, en la medida de lo posible, los reinicios del equipo y explica cómo pueden aprovecharlo las aplicaciones que instalan .NET Framework.|
|[Guía de implementación para administradores](guide-for-administrators.md)|Explica cómo un administrador del sistema puede implementar .NET Framework y sus dependencias del sistema en una red con Microsoft Endpoint Configuration Manager.|
|[Guía de implementación para desarrolladores](deployment-guide-for-developers.md)|Explica cómo los desarrolladores de software pueden instalar .NET Framework en los equipos de los usuarios con sus aplicaciones.|
|[Implementar aplicaciones, servicios y componentes](/visualstudio/deployment/deploying-applications-services-and-components)|Describe las opciones de implementación de Visual Studio e incluye instrucciones para publicar una aplicación mediante las tecnologías ClickOnce y Windows Installer.|
|[Publicar aplicaciones ClickOnce](/visualstudio/deployment/publishing-clickonce-applications)|Describe cómo empaquetar una aplicación de Windows Forms e implementarla con ClickOnce en los equipos cliente en una red.|
|[Empaquetar e implementar recursos](../resources/packaging-and-deploying-resources-in-desktop-apps.md)|Describe el modelo de concentrador y de radio que .NET Framework usa para empaquetar e implementar los recursos; aborda las convenciones de nomenclatura de los recursos, el proceso de reserva y las alternativas de empaquetado.|
|[Implementar una aplicación interoperativa](../interop/deploying-an-interop-application.md)|Explica cómo distribuir e instalar aplicaciones de interoperabilidad, que suelen incluir un ensamblado de cliente de .NET Framework, uno o varios ensamblados de interoperabilidad que representan diferentes bibliotecas de tipos COM, y uno o varios componentes COM registrados.|
|[Cómo: Obtener el progreso del instalador de .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)|Describe cómo iniciar y seguir en modo silencioso el proceso de instalación de .NET Framework, mientras se muestra la vista del progreso de la instalación.|

## <a name="see-also"></a>Vea también

- [Guía de desarrollo](../development-guide.md)
