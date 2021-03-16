---
title: Installutil.exe (Herramienta Installer)
description: Use Installutil.exe, la herramienta de instalación. Esta herramienta permite instalar o desinstalar recursos de servidor mediante la ejecución de los componentes del instalador en los ensamblados especificados.
ms.date: 03/30/2017
helpviewer_keywords:
- uninstalling server resources
- removing server resources
- status information for installation
- installation progress reports
- installing server resources
- Installer tool
- Installutil.exe
- files, Installer tool
- progress information for installation
- reporting installation progress
ms.assetid: 3f9d0533-f895-4897-b4ea-528284e0241d
ms.openlocfilehash: 0e03a2a7033d3e210727e2eb080140ad87240dba
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259946"
---
# <a name="installutilexe-installer-tool"></a>Installutil.exe (Herramienta Installer)

La herramienta de instalación es una utilidad de la línea de comandos que le permite instalar y desinstalar recursos de servidor mediante la ejecución de los componentes del instalador en ensamblados específicos. Esta herramienta funciona junto con clases del espacio de nombres <xref:System.Configuration.Install>.

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).

En el símbolo del sistema, escriba lo siguiente:

## <a name="syntax"></a>Sintaxis

```console
installutil [/u[ninstall]] [options] assembly [[options] assembly] ...
```

## <a name="parameters"></a>Parámetros

|Argumento|Descripción|
|--------------|-----------------|
|`assembly`|Nombre de archivo del ensamblado en el que se ejecutan los componentes del instalador. Omita este parámetro si desea especificar el nombre seguro del ensamblado mediante la opción `/AssemblyName`.|

<a name="options"></a>

## <a name="options"></a>Opciones

|Opción|Descripción|
|------------|-----------------|
|`/h[elp]`<br /><br /> o bien<br /><br /> `/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|
|`/help` *assembly*<br /><br /> o bien<br /><br /> `/?` *assembly*|Muestra opciones adicionales reconocidas por instaladores individuales dentro del ensamblado especificado, junto con la sintaxis y las opciones de los comandos de InstallUtil.exe. Esta opción agrega el texto devuelto por la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> de cada componente del instalador al texto de ayuda de InstallUtil.exe.|
|`/AssemblyName` "*assemblyName*<br /><br /> ,Version=*major.minor.build.revision*<br /><br /> ,Culture=*locale*<br /><br /> ,PublicKeyToken=*publicKeyToken*"|Especifica el nombre seguro de un ensamblado, que debe registrarse en la memoria caché global de ensamblados. El nombre del ensamblado debe ser completo e incluir la versión, la referencia cultural y el token de clave pública. El nombre completo debe ir entre comillas.<br /><br /> Por ejemplo, "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0" es un nombre de ensamblado completo.|
|`/InstallStateDir=[` *directoryName* `]`|Especifica el directorio del archivo .InstallState que contiene los datos usados para desinstalar el ensamblado. El directorio predeterminado es el que contiene el ensamblado.|
|`/LogFile=`[*filename*]|Especifica el nombre del archivo de registro donde se graba el progreso de la instalación. De forma predeterminada, si se omite la opción `/LogFile`, se crea un archivo de registro denominado *assemblyname*.InstallLog. Si se omite *filename*, no se genera ningún archivo de registro.|
|`/LogToConsole`={`true`&#124;`false`}|Si es `true`, muestra el resultado en la consola. Si es `false` (valor predeterminado), el resultado no se muestra en la consola.|
|`/ShowCallStack`|Envía la pila de llamadas al archivo de registro si se produce una excepción en cualquier paso de la instalación.|
|`/u`[`ninstall`]|Desinstala los ensamblados especificados. A diferencia de las demás opciones, `/u` se aplica a todos los ensamblados con independencia del lugar donde aparezca la opción en la línea de comandos.|

<a name="cmdline"></a>

## <a name="additional-installer-options"></a>Opciones adicionales del instalador

Los instaladores individuales utilizados en un ensamblado pueden reconocer opciones adicionales a las enumeradas en la sección [Opciones](#options). Para obtener información sobre estas opciones, ejecute InstallUtil.exe con las rutas de acceso de los ensamblados en la línea de comandos junto con la opción `/?` o `/help`. Para especificar estas opciones, debe incluirlas en la línea de comandos junto con las opciones reconocidas por InstallUtil.exe.

> [!NOTE]
> Texto de ayuda en las opciones admitidas por los componentes individuales del instalador devuelto por la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType>. Es posible obtener acceso mediante programación a las opciones individuales especificadas en la línea de comandos desde la propiedad <xref:System.Configuration.Install.Installer.Context%2A?displayProperty=nameWithType>.

Todas las opciones y parámetros de la línea de comandos se escriben en el archivo de registro de la instalación. Sin embargo, si utiliza el parámetro `/Password`, que reconocen algunos componentes del instalador, la información de la contraseña se reemplazará por ocho asteriscos (*) y no aparecerá en el archivo de registro.

> [!IMPORTANT]
> En algunos casos, los parámetros pasados al instalador pueden incluir información confidencial o de identificación personal que, de forma predeterminada, se escribe en un archivo de registro de texto sin formato. Para impedir este comportamiento, puede suprimir el archivo de registro; para ello, especifique `/LogFile=` (sin el argumento *filename*) después de Installutil.exe en la línea de comandos.

## <a name="remarks"></a>Comentarios

Las aplicaciones de .NET Framework constan de archivos de programa tradicionales y recursos asociados, como colas de mensajes, registros de eventos y contadores de rendimiento que se deben crear al implementar la aplicación. Se pueden utilizar componentes del instalador de un ensamblado para crear estos recursos cuando se instala la aplicación y para quitarlos cuando la aplicación se desinstale. Installutil.exe detecta y ejecuta estos componentes del instalador.

Se pueden especificar varios ensamblados en la misma línea de comandos. Las opciones situadas delante de un nombre de ensamblado se aplican a la instalación de dicho ensamblado. Salvo para `/u` y `/AssemblyName`, las opciones son acumulativas pero reemplazables. Es decir, las opciones especificadas para un ensamblado se aplican a todos los ensamblados posteriores salvo que la opción se especifique con un nuevo valor.

Si se ejecuta Installutil.exe con un ensamblado sin especificar opciones, la herramienta coloca los tres archivos siguientes en el directorio del ensamblado:

- InstallUtil.InstallLog: contiene una descripción general del progreso de la instalación.

- *assemblyname*.InstallLog: contiene información específica para la fase de confirmación del proceso de la instalación. Para obtener más información sobre la fase de confirmación, vea el método <xref:System.Configuration.Install.Installer.Commit%2A>.

- *assemblyname*.InstallState: contiene los datos usados para desinstalar el ensamblado.

Installutil.exe usa la reflexión para inspeccionar los ensamblados especificados y buscar todos los tipos <xref:System.Configuration.Install.Installer> que tengan el atributo <xref:System.ComponentModel.RunInstallerAttribute?displayProperty=nameWithType> establecido en `true`. A continuación, la herramienta ejecuta el método <xref:System.Configuration.Install.Installer.Install%2A?displayProperty=nameWithType> o <xref:System.Configuration.Install.Installer.Uninstall%2A?displayProperty=nameWithType> en cada una de las instancias del tipo <xref:System.Configuration.Install.Installer>. Installutil.exe realiza la instalación de forma transaccional; es decir, si se produce un error en la instalación de uno de los ensamblados, se revierten las instalaciones de los demás ensamblados. El proceso de desinstalación no es transaccional.

Installutil.exe no puede instalar ni desinstalar los ensamblados con firma retrasada, pero puede instalar o desinstalar los ensamblados con nombre seguro.

A partir de la versión 2.0 de .NET Framework, la versión de 32 bits de Common Language Runtime (CLR) se distribuye solo con la versión de 32 bits de la herramienta de instalación, aunque la versión de 64 bits de CLR se distribuye tanto con la versión de 32 bits como con la versión de 64 bits de dicha herramienta. Cuando utilice el CLR de 64 bits, emplee la herramienta de instalación de 32 bits para instalar los ensamblados de 32 bits y la herramienta de instalación de 64 bits para instalar los ensamblados de 64 bits y del Lenguaje intermedio de Microsoft (MSIL). Ambas versiones de la herramienta de instalación se comportan de la misma manera.

No se puede utilizar Installutil.exe para implementar un servicio de Windows creado mediante C++, ya que Installutil.exe no reconoce el código nativo incrustado generado por el compilador de C++. Si intenta implementar un servicio de Windows de C++ con Installutil.exe, se producirá una excepción como <xref:System.BadImageFormatException>. Para trabajar con este escenario, mueva el código de servicio a un módulo de C++ y, a continuación, escriba el objeto del instalador en C# o Visual Basic.

## <a name="examples"></a>Ejemplos

El comando siguiente muestra una descripción de la sintaxis y las opciones de comando para InstallUtil.exe.

```console
installutil /?
```

El comando siguiente muestra una descripción de la sintaxis y las opciones de comando para InstallUtil.exe. También muestra una descripción y la lista de opciones admitidas por los componentes del instalador en `myAssembly.exe` si el texto de ayuda se ha asignado a la propiedad <xref:System.Configuration.Install.Installer.HelpText%2A?displayProperty=nameWithType> del instalador.

```console
installutil /? myAssembly.exe
```

El comando siguiente ejecuta los componentes del instalador en el ensamblado `myAssembly.exe`.

```console
installutil myAssembly.exe
```

El siguiente comando ejecuta los componentes del instalador en un ensamblado mediante el modificador `/AssemblyName` y un nombre completo.

```console
installutil /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

El comando siguiente ejecuta los componentes del instalador en un ensamblado especificado por nombre de archivo y en un ensamblado especificado por nombre seguro. Tenga en cuenta que todos los ensamblados especificados por nombre de archivo deben preceder a los especificados por nombre seguro en la línea de comandos, ya que la opción `/AssemblyName` no se puede invalidar.

```console
installutil myAssembly.exe /AssemblyName "myAssembly, Culture=neutral, PublicKeyToken=0038abc9deabfle5, Version=4.0.0.0"
```

El comando siguiente ejecuta los componentes del desinstalador en el ensamblado `myAssembly.exe`.

```console
installutil /u myAssembly.exe
```

El comando siguiente ejecuta los componentes del desinstalador en los ensamblados `myAssembly1.exe` y `myAssembly2.exe`.

```console
installutil myAssembly1.exe /u myAssembly2.exe
```

Dado que la posición de la opción `/u` en la línea de comandos no es importante, esta es equivalente al siguiente comando.

```console
installutil /u myAssembly1.exe myAssembly2.exe
```

El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe` y especifica la información del progreso que se escribirá en `myLog.InstallLog`.

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe
```

El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe`, especifica que la información de progreso debe escribirse en `myLog.InstallLog` y usa la opción `/reg` personalizada de los instaladores para especificar las actualizaciones que se deben realizar en el Registro del sistema.

```console
installutil /LogFile=myLog.InstallLog /reg=true myAssembly.exe
```

El comando siguiente ejecuta los instaladores en el ensamblado `myAssembly.exe`, usa la opción `/email` personalizada del instalador para especificar la dirección de correo electrónico del usuario e impide que los resultados se envíen al archivo de registro.

```console
installutil /LogFile= /email=admin@mycompany.com myAssembly.exe
```

El comando siguiente escribe el progreso de instalación de `myAssembly.exe` en `myLog.InstallLog` y el progreso de `myTestAssembly.exe` en `myTestLog.InstallLog`.

```console
installutil /LogFile=myLog.InstallLog myAssembly.exe /LogFile=myTestLog.InstallLog myTestAssembly.exe
```

## <a name="see-also"></a>Vea también

- <xref:System.Configuration.Install>
- [Herramientas](index.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
