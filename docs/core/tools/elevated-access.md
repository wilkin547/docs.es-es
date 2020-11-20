---
title: Acceso con privilegios elevados para comandos de dotnet
description: Obtenga información sobre los procedimientos recomendados para los comandos de dotnet que requieren acceso con privilegios elevados.
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: b34a4d631ec0e5ef641e1ffbc91e081d25645157
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634056"
---
# <a name="elevated-access-for-dotnet-commands"></a>Acceso con privilegios elevados para comandos de dotnet

Los procedimientos recomendados de desarrollo de software sirven de guía a los desarrolladores para escribir software que requiera la menor cantidad de privilegios. Sin embargo, algunos programas, como las herramientas de supervisión de rendimiento, requieren permiso del administrador debido a las reglas del sistema operativo. En las siguientes instrucciones se describen los escenarios admitidos para escribir dicho software con .NET Core.

Los siguientes comandos se pueden ejecutar con privilegios elevados:

- Comandos `dotnet tool`, como [dotnet tool install](dotnet-tool-install.md).
- `dotnet run --no-build`
- `dotnet-core-uninstall`

No se recomienda ejecutar otros comandos con privilegios elevados. En concreto, no se recomienda usar privilegios elevados con los comandos que usa MSBuild, como [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md) y [dotnet run](dotnet-run.md). Los problemas de administración de permisos son el principal problema cuando un usuario cambia varias veces entre una cuenta restringida y otra raíz después de emitir comandos de dotnet. Como usuario restringido, es posible que no tenga acceso al archivo generado por un usuario raíz. Hay maneras de resolver esta situación, pero, para empezar, no es necesario que surjan.

Puede ejecutar comandos como raíz siempre y cuando no cambie repetidas veces entre la raíz y una cuenta restringida. Por ejemplo, los contenedores de Docker se ejecutan como raíz de forma predeterminada, por lo que tienen esta característica.

## <a name="global-tool-installation"></a>Instalación de herramienta global

En las instrucciones siguientes se muestra la manera recomendada de instalar, ejecutar y desinstalar las herramientas de .NET que necesitan privilegios elevados para ejecutarse.

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

### <a name="install-the-tool"></a>Instalación de la herramienta

Si la carpeta `%ProgramFiles%\dotnet-tools` ya existe, siga este procedimiento para comprobar si el grupo "Usuarios" tiene permiso para escribir o modificar ese directorio:

- Haga clic con el botón derecho en la carpeta `%ProgramFiles%\dotnet-tools` y seleccione **Propiedades**. Se abrirá el cuadro de diálogo **Propiedades comunes**.
- Seleccione la pestaña **Seguridad**. En **Nombres de grupos o usuarios**, compruebe si el grupo "Usuarios" tiene permiso para escribir o modificar el directorio.
- Si el grupo "Usuarios" puede escribir o modificar el directorio, al instalar las herramientas, use otro nombre de directorio de *dotnet-tools*.

Para instalar las herramientas, ejecute el siguiente comando en un símbolo del sistema con privilegios elevados. Creará la carpeta *dotnet-tools* durante la instalación.

```dotnetcli
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a>Ejecución de la herramienta global

**Opción 1** Use la ruta de acceso completa con privilegios elevados:

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

**Opción 2** Agregue la carpeta recién creada a `%Path%`. Solo necesita realizar esta operación una vez.

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

Y ejecute con:

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a>Desinstalación de la herramienta global

En un símbolo del sistema con privilegios elevados, escriba el siguiente comando:

```dotnetcli
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linux"></a>[Linux](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macos"></a>[macOS](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a>Herramientas locales

Las herramientas locales se limitan al árbol de subdirectorio, por usuario. Cuando se ejecutan con privilegios elevados, las herramientas locales comparten un entorno de usuario con privilegios restringidos en el entorno con privilegios elevados. En Linux y macOS, esto da como resultado archivos que establecen con acceso de solo usuario raíz. Si el usuario cambia a una cuenta restringida, el usuario ya no podrá acceder a los archivos ni escribir en ellos. Por tanto, no se recomienda instalar las herramientas que necesiten permisos elevados como herramientas locales. En su lugar, use la opción `--tool-path` y las instrucciones anteriores para las herramientas globales.

## <a name="elevation-during-development"></a>Elevación durante el desarrollo

Durante el desarrollo, puede que necesite acceso con privilegios elevados para probar la aplicación. Este escenario es común para las aplicaciones de IoT, por ejemplo. Se recomienda que compile la aplicación sin la elevación y, a continuación, la ejecute con privilegios elevados. Hay unos pocos patrones, como los siguientes:

- Uso de archivo ejecutable generado (proporciona el mejor rendimiento de inicio):

   ```dotnetcli
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```

- Mediante el comando [dotnet run](dotnet-run.md) con la marca `—no-build` para evitar que se generen nuevos archivos binarios:

   ```dotnetcli
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a>Vea también

- [Información general sobre las herramientas de .NET](global-tools.md)
