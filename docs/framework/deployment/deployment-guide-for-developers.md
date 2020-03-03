---
title: Guía de implementación de .NET Framework para desarrolladores
ms.custom: updateeachrelease
ms.date: 01/17/2020
helpviewer_keywords:
- developer's guide, deploying .NET Framework
- deployment [.NET Framework], developer's guide
ms.assetid: 094d043e-33c4-40ba-a503-e0b20b55f4cf
ms.openlocfilehash: 26c168040b0fa5e975e64a7518b0d0bf250c4711
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628129"
---
# <a name="net-framework-deployment-guide-for-developers"></a>Guía de implementación de .NET Framework para desarrolladores
En este tema se proporciona información a los desarrolladores que quieren instalar cualquier versión de .NET Framework a partir de .NET Framework 4.5 en [!INCLUDE[net_current](../../../includes/net-current-version.md)] con sus aplicaciones.

Puede descargar los paquetes de idioma y los paquetes redistribuibles para .NET°Framework desde las páginas de descarga:

- [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
- [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework/net472)
- [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/net471)
- [.NET Framework 4.7](https://dotnet.microsoft.com/download/dotnet-framework/net47)
- [.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)
- [.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)
- [.NET Framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)
- [.NET Framework 4.5.2](https://dotnet.microsoft.com/download/dotnet-framework/net452)
- [.NET Framework 4.5.1](https://dotnet.microsoft.com/download/dotnet-framework/net451)
- [.NET Framework 4.5](https://dotnet.microsoft.com/download/dotnet-framework/net45)

 Notas importantes:

- Las versiones de .NET Framework desde .NET Framework 4.5.1 hasta [!INCLUDE[net_current](../../../includes/net-current-version.md)] son actualizaciones en contexto de .NET Framework 4.5, lo que significa que usan la misma versión de runtime pero las versiones de ensamblado se actualizan e incluyen nuevos tipos y miembros.

- .NET Framework 4.5 y versiones posteriores se compilan de forma incremental en .NET Framework 4. Al instalar .NET Framework 4.5 o versiones posteriores en un sistema que tenga instalado .NET Framework 4, los ensamblados de la versión 4 se reemplazan con nuevas versiones.

- Si hace referencia a un [paquete fuera de banda](../get-started/the-net-framework-and-out-of-band-releases.md) de Microsoft en su aplicación, el ensamblado se incluirá en el paquete de la aplicación.

- Debe tener privilegios de administrador para instalar .NET Framework 4.5 o versiones posteriores.

- .NET Framework 4.5 se incluye en Windows 8 y Windows Server 2012, por lo que no tiene que implementarlo con su aplicación en esos sistemas operativos. De igual forma, .NET Framework 4.5.1 se incluye en Windows 8.1 y Windows Server 2012 R2. .NET Framework 4.5.2 no está incluido en ningún sistema operativo. .NET Framework 4.6 se incluye en Windows 10, .NET Framework 4.6.1 se incluye en la Actualización de noviembre de Windows 10 y .NET Framework 4.6.2 se incluye en la Actualización de aniversario de Windows 10.  .NET Framework 4.7 se incluye en Windows 10 Creators Update; .NET Framework 4.7.1 se incluye en Windows 10 Fall Creators Update y .NET Framework 4.7.2 se incluye en la Actualización de octubre de 2018 de Windows 10 y en la Actualización de abril de 2018 de Windows 10. .NET Framework 4.8 se incluye en la Actualización de mayo de 2019 de Windows 10. Para obtener una lista completa de los requisitos de hardware y software, vea [Requisitos de sistema](../get-started/system-requirements.md).

- A partir de .NET Framework 4.5, los usuarios pueden ver una lista de aplicaciones de .NET Framework en ejecución durante la instalación y cerrarlas fácilmente. Esto puede ayudar a evitar el reinicio del sistema causado por las instalaciones de .NET Framework. Vea [Reducir los reinicios del sistema](reducing-system-restarts.md).

- La desinstalación de .NET Framework 4.5 o versiones posteriores también quita los archivos de .NET Framework 4 ya existentes. Si desea volver a .NET Framework 4, deberá reinstalarlo, así como todas sus actualizaciones. Vea [Instalación de .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5a4x27ek(v=vs.100)).

- .NET Framework 4.5 redistribuible se actualizó el 9 de octubre de 2012 para corregir un problema relacionado con una marca de tiempo incorrecta en un certificado digital, que produjo que la firma digital en los archivos mostrados y firmados por Microsoft expirase prematuramente. Si anteriormente instaló el paquete redistribuible de .NET Framework 4.5 con fecha del 16 de agosto de 2012, es recomendable que actualice su copia con el último redistribuible de la [página de descarga de .NET Framework](https://dotnet.microsoft.com/download/dotnet-framework/net45). Para obtener más información sobre este problema, vea el [Documento informativo sobre seguridad de Microsoft 2749655](https://docs.microsoft.com/security-updates/SecurityAdvisories/2012/2749655).

Para obtener información sobre cómo un administrador del sistema puede implementar .NET Framework y sus dependencias del sistema en una red, vea [Deployment Guide for Administrators](guide-for-administrators.md) (Guía de implementación para administradores).

## <a name="deployment-options-for-your-app"></a>Opciones de implementación para la aplicación

Cuando esté listo para publicar la aplicación en un servidor web u otra ubicación centralizada para que los usuarios puedan instalarla, puede elegir varios métodos de implementación. Algunos de estos se proporcionan con Visual Studio. En la tabla siguiente se muestran las opciones de implementación para una aplicación y se especifica el paquete redistribuible de .NET Framework que admite cada opción. Además, puede escribir un programa de instalación personalizado para su aplicación; para obtener más información, vea la sección [Encadenar la instalación de .NET Framework en la instalación de la aplicación](#chaining).

|Estrategia de implementación para la aplicación|Métodos de implementación disponibles|Paquete redistribuible de .NET Framework para utilizar|
|--------------------------------------|----------------------------------|-------------------------------------------|
|Instalar desde Internet|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Conjunto de herramientas de WiX](#wix)<br />- [Instalación manual](#installing_manually)|[Web installer](#redistributable-packages)|
|Instalar desde disco|- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Conjunto de herramientas de WiX](#wix)<br />- [Instalación manual](#installing_manually)|[Offline installer](#redistributable-packages)|
|Instalar desde una red de área local (para aplicaciones empresariales)|- [ClickOnce](#clickonce-deployment)|Ya sea el [instalador web](#redistributable-packages) (vea [ClickOnce](#clickonce-deployment) para obtener información sobre las restricciones) o el [instalador sin conexión](#redistributable-packages)|

## <a name="redistributable-packages"></a>Paquetes redistribuibles

.NET Framework está disponible en dos paquetes redistribuibles: instalador web (arranque) e instalador sin conexión (independiente redistribuible). Todas las descargas de .NET Framework se hospedan en la [página Descargar .NET Framework](https://dotnet.microsoft.com/download/dotnet-framework/). En la tabla siguiente se comparan los dos paquetes:

||instalador web|instalador sin conexión|
|-|-------------------|-----------------------|
|¿Requiere conexión a Internet?|Sí|No|
|Tamaño de la descarga|Menor (incluye solo el instalador para la plataforma de destino)*|Mayor*|
|Paquetes de idioma|Se incluye**|Debe [instalarse por separado](#chain_langpack), a menos que utilice el paquete destinado a todos los sistemas operativos|
|Método de implementación|Admite todos los métodos:<br /><br />- [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Instalación manual](#installing_manually)<br />- [Instalación personalizada (encadenamiento)](#chaining)|Admite todos los métodos:<br /><br /> - [ClickOnce](#clickonce-deployment)<br />- [InstallAware](#installaware-deployment)<br />- [InstallShield](#installshield-deployment)<br />- [Windows Installer XML (WiX)](#wix)<br />- [Instalación manual](#installing_manually)<br />- [Instalación personalizada (encadenamiento)](#chaining)|

\* El tamaño del instalador sin conexión es mayor porque contiene componentes para todas las plataformas de destino. Cuando termine de ejecutar la instalación, el sistema operativo Windows almacenará en caché solo el instalador que se utilizó. Si se elimina el instalador sin conexión después de la instalación, el espacio en disco utilizado es el mismo que el instalador web utiliza. Si la herramienta que utiliza (por ejemplo, [InstallAware](#installaware-deployment) or [InstallShield](#installshield-deployment)) para crear el programa de instalación de la aplicación proporciona una carpeta de archivos de configuración que se quita después de la instalación, el instalador sin conexión se puede eliminar automáticamente colocándolo en la carpeta de configuración.

\*\* Si utiliza el instalador web con la instalación personalizada, puede usar la configuración de idioma predeterminada basada en la configuración de interfaz de usuario multilingüe (MUI) del usuario o especificar otro paquete de idioma mediante la opción `/LCID` en la línea de comandos. Vea la sección [Encadenar mediante la interfaz de usuario predeterminada de .NET Framework](#chaining_default) para obtener ejemplos.

## <a name="deployment-methods"></a>Métodos de implementación

 Hay cuatro métodos de implementación disponibles:

- Puede establecer una dependencia en .NET Framework. Puede especificar .NET Framework como un requisito previo en la instalación de la aplicación mediante uno de estos métodos:

  - Usar la [implementación de ClickOnce](#clickonce-deployment) (disponible en Visual Studio)

  - Cree un [proyecto de InstallAware](#installaware-deployment) (hay una edición gratuita disponible para los usuarios de Visual Studio)

  - Crear un [proyecto de InstallShield](#installshield-deployment) (disponible con Visual Studio)

  - Usar el [conjunto de herramientas de Windows Installer (WiX)](#wix)

- Puede pedir a los usuarios que [instalen manualmente .NET Framework](#installing_manually).

- Puede encadenar (incluir) el proceso de instalación de .NET Framework en la instalación de la aplicación y decidir cómo desea controlar la experiencia de instalación de .NET Framework:

  - [Usar la interfaz de usuario predeterminada](#chaining_default). Deje que el instalador de .NET Framework proporcione la experiencia de instalación.

  - [Personalizar la interfaz de usuario](#chaining_custom) para presentar una experiencia de instalación unificada y supervisar el progreso de instalación de .NET Framework.

Estos métodos de implementación se describen con mayor detalle en las siguientes secciones.

## <a name="setting-a-dependency-on-the-net-framework"></a>Establecer una dependencia en .NET Framework

Si utiliza ClickOnce, InstallAware, InstallShield o WiX para implementar la aplicación, puede agregar una dependencia en .NET Framework para poder instalarla como parte de la aplicación.

### <a name="clickonce-deployment"></a>implementación de ClickOnce

La implementación ClickOnce está disponible para proyectos creados en Visual Basic y Visual C#, pero no está disponible para Visual C++.

En Visual Studio, elija la implementación de ClickOnce y agregue una dependencia en .NET Framework:

1. Abra el proyecto de aplicación que desea publicar.

2. En el Explorador de soluciones, abra el menú contextual del proyecto y, a continuación, elija **Propiedades**.

3. Elija el panel **Publicar** .

4. Elija el botón **Requisitos previos** .

5. En el cuadro de diálogo **Requisitos previos** , asegúrese de que está activada la casilla **Crear programa de instalación para instalar los componentes necesarios** .

6. En la lista de requisitos previos, busque y seleccione la versión de .NET Framework que haya usado para compilar el proyecto.

7. Elija una opción para especificar la ubicación de origen de los requisitos previos y, a continuación, elija **Aceptar**.

     Si proporciona una dirección URL para la ubicación de descarga de .NET Framework, puede especificar la página de descarga de .NET Framework o un sitio propio. Si va a colocar el paquete redistribuible en su propio servidor, debe usar el instalador sin conexión, no el instalador web. Solo se puede vincular al instalador web en la página de descarga de .NET Framework. La dirección URL también puede ser un disco en el que se distribuye su propia aplicación.

8. En el cuadro de diálogo **Páginas de propiedades** , elija **Aceptar**.

<a name="installaware"></a>

### <a name="installaware-deployment"></a>Implementación de InstallAware

InstallAware compila paquetes de aplicación de Windows (APPX), Windows Installer (MSI), Native Code (EXE) y App-V (Application Virtualization) desde un único origen. [Incluya fácilmente cualquier versión de .NET Framework](https://www.installaware.com/one-click-pre-requisite-installer.htm) en su instalación, personalizando de manera opcional la instalación mediante la [edición de los scripts predeterminados](https://www.installaware.com/msicode.htm). Por ejemplo, InstallAware instala previamente certificados en Windows 7, sin lo cual la instalación de .NET Framework 4.7 genera un error. Para obtener más información sobre InstallAware, consulte el sitio web de [InstallAware para Windows Installer](https://www.installaware.com/).

### <a name="installshield-deployment"></a>Implementación de InstallShield

InstallShield compila paquetes de aplicaciones de Windows (MSIX, APPX), paquetes de Windows Installer (MSI) e instaladores de código nativo (EXE). InstallShield también proporciona integración con Visual Studio. Para obtener más información, vea el sitio web de [InstallShield](https://www.flexerasoftware.com/install/products/installshield.html).

<a name="wix"></a>

### <a name="windows-installer-xml-wix-deployment"></a>Implementación de Windows Installer XML (WiX)

El conjunto de herramientas de Windows Installer XML (WiX) compila paquetes de instalación de Windows desde el código fuente XML. WiX es compatible con un entorno de línea de comandos que se puede integrar en los procesos de compilación para crear paquetes de instalación MSI y MSM. Al utilizar WiX, podrá [especificar .NET Framework como requisito previo](https://wixtoolset.org/documentation/manual/v3/howtos/redistributables_and_install_checks/install_dotnet.html)o [crear un encadenador](https://wixtoolset.org/documentation/manual/v3/xsd/wix/exepackage.html) para controlar completamente la experiencia de implementación de .NET Framework. Para obtener más información sobre WiX, vea el sitio web [Conjunto de herramientas de Windows Installer XML (WiX)](https://wixtoolset.org/) .

<a name="installing_manually"></a>

## <a name="installing-the-net-framework-manually"></a>Instalar .NET Framework manualmente

En algunas situaciones, puede no ser práctico instalar automáticamente .NET Framework con la aplicación. En esos casos, puede dejar que los usuarios instalen .NET Framework por su cuenta. El paquete redistribuible está disponible en [dos paquetes](#redistributable-packages). En el proceso de instalación, ofrezca instrucciones a los usuarios para que localicen e instalen .NET Framework.

<a name="chaining"></a>

## <a name="chaining-the-net-framework-installation-to-your-apps-setup"></a>Encadenar la instalación de .NET Framework en la instalación de la aplicación

Si está creando un programa de instalación personalizado para una aplicación, puede encadenar (incluir) el proceso de instalación de .NET Framework en el proceso de instalación de la aplicación. El encadenamiento proporciona dos opciones de interfaz de usuario para la instalación de .NET Framework:

- Utilizar la interfaz de usuario predeterminada proporcionada por el instalador de .NET Framework.

- Crear una interfaz de usuario personalizada para la instalación de .NET Framework para mantener la coherencia con el programa de instalación de la aplicación.

Ambos métodos permiten utilizar el instalador web o el instalador sin conexión. Cada paquete tiene sus ventajas:

- Si utiliza el instalador web, el proceso de instalación de .NET Framework decide qué paquete de instalación es necesario y descarga e instala solo ese paquete desde Internet.

- Si utiliza el instalador sin conexión, puede incluir el conjunto completo de paquetes de instalación de .NET Framework con los discos de redistribución para que los usuarios no tengan que descargar archivos adicionales desde Internet durante la instalación.

<a name="chaining_default"></a>

### <a name="chaining-by-using-the-default-net-framework-ui"></a>Encadenar mediante la interfaz de usuario predeterminada de .NET Framework

Para encadenar de forma silenciosa el proceso de instalación de .NET Framework y dejar que el instalador de .NET Framework proporcione la interfaz de usuario, agregue el siguiente comando al programa de instalación:

`<.NET Framework redistributable> /q /norestart /ChainingPackage <PackageName>`

Por ejemplo, si el programa ejecutable es Contoso.exe y desea instalar el paquete redistribuible sin conexión de .NET Framework 4.5 de forma silenciosa, utilice el comando:

`dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage Contoso`

Puede utilizar las opciones de línea de comandos adicionales para personalizar la instalación. Por ejemplo:

- Para proporcionar un método para que los usuarios cierren las aplicaciones de .NET Framework que estén en ejecución con el fin de minimizar los reinicios del sistema, establezca el modo pasivo y utilice la opción `/showrmui` de la forma siguiente:

    `dotNetFx45_Full_x86_x64.exe /norestart /passive /showrmui /ChainingPackage Contoso`

     Este comando permite reiniciar el administrador para mostrar un cuadro de mensaje que proporciona a los usuarios la oportunidad de cerrar las aplicaciones de .NET Framework antes de instalar el componente.

- Si está utilizando el instalador web, puede utilizar la opción `/LCID` para especificar un paquete de idioma. Por ejemplo, para encadenar el instalador web de .NET Framework 4.5 en el programa de instalación de Contoso e instalar el paquete de idioma japonés, agregue el siguiente comando al proceso de instalación de la aplicación:

    `dotNetFx45_Full_setup.exe /q /norestart /ChainingPackage Contoso /LCID 1041`

     Si se omite la opción `/LCID` , el programa de instalación instalará el paquete de idioma que coincida con la configuración de MUI del usuario.

    > [!NOTE]
    > Los distintos paquetes de idioma pueden tener fechas de versión diferentes. Si el paquete de idioma especificado no está disponible en el centro de descarga, el programa de instalación instalará .NET Framework sin el paquete de idioma. Si .NET Framework ya está instalado en el equipo del usuario, el archivo de instalación solo instalará el paquete de idioma.

Para obtener una lista completa de opciones, vea la sección [Opciones de la línea de comandos](#command-line-options) .

Para ver los códigos de retorno comunes, consulte la sección [Códigos de retorno](#return-codes) .

<a name="chaining_custom"></a>

### <a name="chaining-by-using-a-custom-ui"></a>Encadenar mediante una interfaz de usuario personalizada

Si tiene un paquete de instalación personalizada, puede iniciar en modo silencioso y realizar un seguimiento de la instalación de .NET Framework mientras se muestra su propia vista del progreso de la instalación. Si es este el caso, asegúrese de controlar lo siguiente en el código:

- Compruebe si hay [requisitos de hardware y software para .NET Framework](../get-started/system-requirements.md).

- [Detecte](#detect_net) si la versión correcta de .NET Framework está ya instalada en el equipo del usuario.

    > [!IMPORTANT]
    > Para determinar si ya está instalada la versión correcta de .NET Framework, debe comprobar si está instalada la versión de destino *o* una versión posterior, no si está instalada la versión de destino. En otras palabras, debe evaluar si la clave de versión recuperada del registro es mayor o igual que la clave de versión de la versión de destino, *no* si es igual a la clave de versión de la versión de destino.

- [Detecte](#detecting-the-language-packs) si los paquetes de idioma ya están instalados en el equipo del usuario.

- Si quiere controlar la implementación, inicie la instalación de forma silenciosa y realice el seguimiento del proceso de instalación de .NET Framework (vea [Cómo: Obtener el progreso del instalador de .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)).

- Si está implementando el instalador sin conexión, [encadene los paquetes de idioma por separado](#chain_langpack).

- Personalice la implementación mediante las [opciones de la línea de comandos](#command-line-options). Por ejemplo, si va a encadenar el instalador web de .NET Framework, pero desea reemplazar el paquete de idioma predeterminado, utilice la opción `/LCID` , tal como se describe en la sección anterior.

- [Solución de problemas](#troubleshooting).

<a name="detect_net"></a>

### <a name="detecting-the-net-framework"></a>Detectar .NET Framework

El instalador de .NET Framework escribe las claves del Registro cuando la instalación es correcta. Puede probar si tiene .NET Framework 4.5 o una versión posterior instalada comprobando que en la carpeta `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` del registro hay un valor `DWORD` denominado `Release`. (Tenga en cuenta que "NET Framework Setup" no comienza con un punto). La existencia de esta clave indica que .NET Framework 4.5 o una versión posterior se ha instalado en ese equipo. El valor de `Release` indica qué versión de .NET Framework está instalada.

> [!IMPORTANT]
> Debe comprobar si hay un valor  **igual o mayor que** el valor de la palabra clave de la versión al tratar de detectar si hay una versión específica.

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|Versión|Valor DWORD de la versión|
|-------------|--------------------------------|
|.NET Framework 4.8 instalado en la Actualización de mayo de 2019 de Windows 10|528040|
|.NET Framework 4.8 instalado en todas las versiones del sistema operativo diferentes de la Actualización de mayo de 2019 de Windows 10|528049|
|.NET Framework 4.7.2 instalado en la Actualización de abril de 2018 de Windows 10 y en Windows Server, versión 1803|461808|
|.NET Framework 4.7.2 instalado en todas las versiones del sistema operativo diferentes de la Actualización de abril de 2018 de Windows 10 y Windows Server, versión 1803. Esto incluye la Actualización de octubre de 2018 de Windows 10. |461814|
|.NET Framework 4.7.1 instalado en Windows 10 Fall Creators Update y en Windows Server, versión 1709|461308|
|.NET Framework 4.7.1 instalado en todas las versiones del sistema operativo diferentes de Windows 10 Fall Creators Update y Windows Server, versión 1709|461310|
|.NET Framework 4.7 instalado en Windows 10 Creators Update|460798|
|.NET Framework 4.7 instalado en todas las versiones del sistema operativo diferentes de Windows 10 Creators Update|460805|
|.NET Framework 4.6.2 instalado en Windows 10 Anniversary Edition y en Windows Server 2016|394802|
|.NET Framework 4.6.2 instalado en todas las versiones de sistema operativo diferentes de Windows 10 Anniversary Edition y Windows Server 2016|394806|
|.NET Framework 4.6.1 instalado en la Actualización de noviembre de Windows 10|394254|
|.NET Framework 4.6.1 instalado en todas las versiones del sistema operativo diferentes de la Actualización de noviembre de Windows 10|394271|
|.NET Framework 4.6 instalado en Windows 10|393295|
|.NET Framework 4.6 instalado en todas las versiones del sistema operativo diferentes de Windows 10|393297|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.5.1 instalado con Windows 8.1 o Windows Server 2012 R2|378675|
|.NET Framework 4.5.1 instalado en Windows 8 y Windows 7|378758|
|.NET Framework 4.5|378389|

### <a name="detecting-the-language-packs"></a>Detectar paquetes de idioma

Puede asegurarse de que se ha instalado un paquete de idioma determinado si comprueba que la carpeta HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\\*LCID* del Registro tiene un valor DWORD denominado `Release`. (Tenga en cuenta que "NET Framework Setup" no comienza con un punto). *LCID* especifica un identificador de configuración regional. Vea [Idiomas compatibles](#supported-languages) para obtener una lista de ellos.

Por ejemplo, para detectar si ya está instalado el paquete de idioma japonés completo (LCID=1041), recupere el siguiente valor con nombre en el Registro:

| | |
|-|-|
| Key | HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\1041 |
| NOMBRE | Release |
| Tipo | DWORD |

Para averiguar si la versión de lanzamiento final de un paquete de idioma está instalada para una versión concreta de NET Framework entre 4.5 y 4.7.2, compruebe el valor DWORD de la clave RELEASE descrita en la sección anterior, [Detectar .NET Framework](#detect_net).

<a name="chain_langpack"></a>

### <a name="chaining-the-language-packs-to-your-app-setup"></a>Encadenar los paquetes de idioma a la instalación de la aplicación

.NET Framework proporciona un conjunto de archivos ejecutables de paquetes de idioma independientes que contienen recursos localizados para referencias culturales específicas. Los paquetes de idioma están disponibles en las páginas de descarga de .NET Framework:

- [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
- [.NET Framework 4.7.2](https://dotnet.microsoft.com/download/dotnet-framework/net472)
- [.NET Framework 4.7.1](https://dotnet.microsoft.com/download/dotnet-framework/net471)
- [.NET Framework 4.7](https://dotnet.microsoft.com/download/dotnet-framework/net47)
- [.NET Framework 4.6.2](https://dotnet.microsoft.com/download/dotnet-framework/net462)
- [.NET Framework 4.6.1](https://dotnet.microsoft.com/download/dotnet-framework/net461)
- [.NET Framework 4.6](https://dotnet.microsoft.com/download/dotnet-framework/net46)
- [.NET Framework 4.5.2](https://dotnet.microsoft.com/download/dotnet-framework/net452)
- [.NET Framework 4.5.1](https://dotnet.microsoft.com/download/dotnet-framework/net451)
- [.NET Framework 4.5](https://dotnet.microsoft.com/download/dotnet-framework/net45)

> [!IMPORTANT]
> Los paquetes de idioma no contienen los componentes de .NET Framework necesarios para ejecutar una aplicación; debe instalar .NET Framework mediante el instalador web o sin conexión para poder instalar un paquete de idioma.

A partir de .NET Framework 4.5.1, los nombres de paquete adoptan la forma NDP<`version`>-KB<`number`>-x86-x64-AllOS-<`culture`> .exe, donde `version` es el número de versión de .NET Framework, `number` es un número de artículo de Microsoft Knowledge Base y `culture` especifica un [país o región](#supported-languages). Un ejemplo de uno de estos paquetes es `NDP452-KB2901907-x86-x64-AllOS-JPN.exe`. Los nombres de paquete se enumeran en la sección [Redistributable Packages](#redistributable-packages) anterior de este artículo.

Para instalar un paquete de idioma con el instalador sin conexión de .NET Framework, debe encadenarlo al programa de instalación de la aplicación. Por ejemplo, para implementar un instalador sin conexión de .NET Framework 4.5.1 con el paquete de idioma japonés, utilice el comando siguiente:

`NDP451-KB2858728-x86-x64-AllOS-JPN.exe /q /norestart /ChainingPackage <ProductName>`

No tiene que encadenar los paquetes de idioma si utiliza el instalador web, ya que el programa de instalación instalará el paquete de idioma que coincida con la configuración de MUI del usuario. Si desea instalar un idioma diferente, puede utilizar la opción `/LCID` para especificar un paquete de idioma.

Para obtener una lista completa de opciones de la línea de comandos, vea la sección [Opciones de la línea de comandos](#command-line-options) .

### <a name="troubleshooting"></a>Solución de problemas

#### <a name="return-codes"></a>Códigos de retorno

En la tabla siguiente se muestra una lista de los códigos de retorno más comunes del instalador redistribuible de .NET Framework. Los códigos devueltos son los mismos para todas las versiones del instalador. Para obtener vínculos a la información detallada, vea la sección siguiente.

|Código devuelto|Descripción|
|-----------------|-----------------|
|0|La instalación se completó correctamente.|
|1602|El usuario canceló la instalación.|
|1603|Error irrecuperable durante la instalación.|
|1641|Para completar la instalación es necesario reiniciar. Este mensaje indica que la instalación se realizó correctamente.|
|3010|Para completar la instalación es necesario reiniciar. Este mensaje indica que la instalación se realizó correctamente.|
|5100|El equipo del usuario no cumple los requisitos del sistema.|

#### <a name="download-error-codes"></a>Descargar códigos de error

Vea el contenido siguiente:

- [Códigos de error del Servicio de transferencia inteligente en segundo plano (BITS)](https://go.microsoft.com/fwlink/?LinkId=180946)

- [Códigos de error del moniker de dirección URL](https://go.microsoft.com/fwlink/?LinkId=180947)

- [Códigos de error de WinHttp](https://go.microsoft.com/fwlink/?LinkId=180948)

#### <a name="other-error-codes"></a>Otros códigos de error

Vea el contenido siguiente:

- [Códigos de error de Windows Installer](https://go.microsoft.com/fwlink/?LinkId=180949)

- [Códigos de resultado del Agente de Windows Update](https://go.microsoft.com/fwlink/?LinkId=180951)

## <a name="uninstalling-the-net-framework"></a>Desinstalar .NET Framework

A partir de Windows 8, puede desinstalar .NET Framework 4.5 o versiones posteriores mediante **Activar o desactivar las características** de Windows en el Panel de control. En versiones anteriores de Windows, puede desinstalar .NET Framework 4.5 o versiones posteriores mediante **Agregar o quitar programas** en el Panel de control.

> [!IMPORTANT]
> Para Windows 7 y sistemas operativos anteriores, al desinstalar .NET Framework 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 o 4.8 no se restauran los archivos de .NET Framework 4.5, y al desinstalar .NET Framework 4.5 no se restauran los archivos de .NET Framework 4. Si desea volver a la versión anterior, debe reinstalarla, así como todas sus actualizaciones.

## <a name="appendix"></a>Apéndice

### <a name="command-line-options"></a>Opciones de la línea de comandos

En la tabla siguiente se muestran las opciones que se pueden incluir cuando se encadenan paquetes redistribuibles de .NET Framework 4.5 al programa de instalación de una aplicación.

|Opción|Descripción|
|------------|-----------------|
|**/CEIPConsent**|Sobrescribe el comportamiento predeterminado y envía comentarios anónimos a Microsoft para mejorar las experiencias de implementación futuras. Se puede utilizar esta opción solamente si el programa de instalación solicita el consentimiento y si el usuario concede el permiso para enviar comentarios anónimos a Microsoft.|
|**/chainingpackage** `packageName`|Especifica el nombre del archivo ejecutable que realiza el encadenamiento. Esta información se envía a Microsoft como comentarios anónimos para ayudar a mejorar las experiencias de implementación futuras.<br /><br /> Si el nombre del paquete incluye espacios, use comillas dobles como delimitadores; por ejemplo: **/chainingpackage "Lucerne Publishing"**. Para obtener un ejemplo de un paquete de encadenamiento, vea [Información de progreso de un paquete de instalación](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100)).|
|**/LCID**  `LCID`<br /><br /> donde `LCID` especifica un identificador de configuración regional (vea [Idiomas compatibles](#supported-languages))|Instala el paquete de idioma especificado por `LCID` y obliga a mostrar la interfaz de usuario indicada en ese idioma, a no ser que se establezca el modo silencio.<br /><br /> En el instalador web, esta opción instala de forma encadenada el paquete de idioma desde Internet. **Nota:**  Use esta opción solo con el instalador web.|
|**/log** `file` &#124; `folder`|Especifica la ubicación del archivo de registro. El valor predeterminado es la carpeta temporal para el proceso y el nombre de archivo predeterminado se basa en el paquete. Si la extensión de archivo es .txt, se genera un registro de texto. Si especifica cualquier otra extensión o no especifica ninguna, se crea un registro HTML.|
|**/msioptions**|Especifica opciones que se pasarán para los elementos .msi y .msp; por ejemplo: `/msioptions "PROPERTY1='Value'"`.|
|**/norestart**|Evita que el programa de instalación se reinicie automáticamente. Si usa esta opción, la aplicación de encadenamiento tiene que capturar el código de retorno y controlar el reinicio (vea [Información de progreso de un paquete de instalación](https://docs.microsoft.com/previous-versions/cc825975(v=vs.100))).|
|**/passive**|Establece el modo pasivo. Muestra la barra de progreso para indicar que la instalación está en curso, pero no muestra ningún indicador ni mensajes de error al usuario. En este modo, cuando se encadena mediante un programa de instalación, el paquete de encadenamiento debe controlar los [códigos de retorno](#return-codes).|
|**/pipe**|Crea un canal de comunicación para permitir que un paquete encadenado obtenga el progreso.|
|**/promptrestart**|Solo en modo pasivo, si el programa de instalación necesita un reinicio, se lo pide al usuario. Esta opción requiere interacción con el usuario si se requiere un reinicio.|
|**/q**|Establece el modo silencioso.|
|**/repair**|Activa la funcionalidad de reparación.|
|**/serialdownload**|Fuerza que la instalación solo tenga lugar después de que se haya descargado el paquete.|
|**/showfinalerror**|Establece el modo pasivo. Muestra los errores solo si la instalación no es correcta. Esta opción requiere interacción con el usuario si la instalación no es correcta.|
|**/showrmui**|Solo se usa con la opción **/passive** . Muestra un cuadro de mensaje que pide a los usuarios que cierren las aplicaciones de .NET Framework que se estén ejecutando actualmente. Este cuadro de mensaje se comporta igual en modo pasivo y no pasivo.|
|**/uninstall**|Desinstala el paquete redistribuible de .NET Framework.|

### <a name="supported-languages"></a>Idiomas compatibles

En la tabla siguiente se enumeran los paquetes de idioma de .NET Framework que están disponibles para .NET Framework 4.5 y versiones posteriores.

|LCID|Idioma (país/región)|culture|
|----------|--------------------------------|-------------|
|1025|Árabe (Arabia Saudí)|ar|
|1028|Chino – Tradicional|zh-Hant|
|1029|Checo|cs|
|1030|Danés|da|
|1031|Alemán – Alemania|de|
|1032|Griego|el|
|1035|Finlandés|fi|
|1036|Francés – Francia|fr|
|1037|Hebreo|he|
|1038|Húngaro|hu|
|1040|Italiano – Italia|it|
|1041|Japonés|ja|
|1042|Coreano|ko|
|1043|Neerlandés – Países Bajos|nl|
|1044|Noruego (Bokmål)|No|
|1045|Polaco|pl|
|1046|Portugués – Brasil|pt-BR|
|1049|Ruso|ru|
|1053|Sueco|sv|
|1055|Turco|tr|
|2052|Chino – Simplificado|zh-Hans|
|2070|Portugués – Portugal|pt-PT|
|3082|Español - España (alfab. internacional)|es|

## <a name="see-also"></a>Vea también

- [Guía de implementación para administradores](guide-for-administrators.md)
- [Requisitos del sistema](../get-started/system-requirements.md)
- [Instalación de .NET Framework para desarrolladores](../install/guide-for-developers.md)
- [Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework](../install/troubleshoot-blocked-installations-and-uninstallations.md)
- [Reducir los reinicios del sistema durante las instalaciones de .NET Framework 4.5](reducing-system-restarts.md)
- [Cómo: Obtener el progreso del instalador de .NET Framework 4.5](how-to-get-progress-from-the-dotnet-installer.md)
