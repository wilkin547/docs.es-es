---
title: Fuslogvw.exe (Visor de registro de enlaces de ensamblados)
description: Use Fuslogvw.exe, el visor de registro de enlaces de ensamblados. Este visor muestra los detalles de los enlaces de ensamblados, lo que ayuda a diagnosticar por qué .NET no encuentra un ensamblado en tiempo de ejecución.
ms.date: 03/30/2017
helpviewer_keywords:
- failed assembly binds
- Fuslogvw.exe
- displaying failed assembly bind details
- assemblies [.NET Framework], failed assembly binds
- locating assemblies
- Assembly Binding Log Viewer
ms.assetid: e32fa443-0778-4cc3-bf36-5c8ea297d296
ms.openlocfilehash: d9c028507c19ef8599e58b38dcdf15af2ede1dee
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259283"
---
# <a name="fuslogvwexe-assembly-binding-log-viewer"></a>Fuslogvw.exe (Visor de registro de enlaces de ensamblados)

El Visor de registro de enlaces de ensamblados es una herramienta que muestra los detalles de los enlaces de ensamblados. Esta información ayuda a diagnosticar la causa por la que .NET Framework no puede encontrar un ensamblado en tiempo de ejecución. Normalmente, estos errores se deben a que el ensamblado se ha implementado en una ubicación incorrecta, a que una imagen nativa ha dejado de ser válida o a que los números de versiones o referencias culturales no coinciden. Normalmente, el error de Common Language Runtime al localizar un ensamblado se muestra como <xref:System.TypeLoadException> en la aplicación.

> [!IMPORTANT]
> Debe ejecutar fuslogvw.exe con privilegios de administrador.

Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell) con credenciales de administrador.

En el símbolo del sistema, escriba el siguiente comando:

```console
fuslogvw
```

El visor muestra una entrada para cada enlace de ensamblado con errores. Para cada error, el visor describe:

- la aplicación que inició el enlace,
- el ensamblado con el que se va a enlazar, incluidos el nombre, la versión, la referencia cultural y la clave pública y
- la fecha y hora del error.

## <a name="how-to"></a>Cómo…

- [Cambiar la vista de la ubicación del registro](#change-the-log-location-view)
- [Ver los detalles de un error específico](#view-details-about-a-specific-failure)
- [Eliminar entradas](#delete-entries)
- [Actualizar la interfaz de usuario](#refresh-the-user-interface)
- [Cambiar la configuración de registro](#change-the-log-settings)
- [Ver el cuadro de diálogo Acerca de](#view-the-about-dialog)

### <a name="change-the-log-location-view"></a>Cambiar la vista de la ubicación del registro

1. Seleccione el botón de opción **Predeterminado** para ver los errores de enlaces de todos los tipos de aplicaciones. De forma predeterminada, las entradas del registro se almacenan por directorios de usuario en la memoria caché wininet del disco.

2. Seleccione el botón de opción **Personalizar** para ver los errores de enlaces en un directorio determinado. Debe especificar la ubicación personalizada en la que quiere que el tiempo de ejecución almacene los registros; para ello, establezca la ubicación del registro predeterminada en un nombre de directorio válido en el cuadro de diálogo **Configuración de registro**. Este directorio debe estar limpio y solo debe contener los archivos que genere el runtime. Si contiene un ejecutable que genera un error que se deba registrar, este no se registrará porque la herramienta intenta crear un directorio con el mismo nombre que el ejecutable. Además, los intentos de ejecutar archivos ejecutables desde la ubicación del registro generarán un error.

    > [!NOTE]
    > Es preferible usar la ubicación de enlace predeterminada en lugar de la ubicación de enlace personalizada. El runtime almacena la ubicación de enlace predeterminada en la memoria caché wininet que, de esta forma, se limpia automáticamente. Si especifica una ubicación de enlace personalizada, es responsabilidad suya limpiarla.

### <a name="view-details-about-a-specific-failure"></a>Ver los detalles de un error específico

1. Seleccione en el visor el nombre de la aplicación de la entrada que desea ver.

2. Haga clic en el botón **Ver registro**. Otra posibilidad es hacer doble clic en la entrada seleccionada.

    La herramienta muestra los siguientes detalles sobre el error de enlace seleccionado:

    - El motivo específico del error del enlace, como "Archivo no encontrado" o "No coinciden las versiones".

    - Información sobre la aplicación que inició el enlace, incluidos el nombre y el directorio raíz de la aplicación (AppBase) y una descripción de la ruta de acceso de búsqueda privada, si existe.

    - La identidad del ensamblado que busca la herramienta.

    - Una descripción de las directivas de versión (aplicación, edición o administrador) que se han aplicado.

    - Si se ha encontrado el ensamblado en la [caché global de ensamblados](../app-domains/gac.md).

    - Una lista de todas las direcciones URL de búsqueda.

En el siguiente ejemplo de entrada del registro se muestra información detallada sobre un enlace de ensamblado con errores.

```output
*** Assembly Binder Log Entry  (3/5/2007 @ 12:54:20 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  C:\WINNT\Microsoft.NET\Framework\v2.0.50727\fusion.dll
Running under executable  C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\graphicfailtest.exe
--- A detailed error log follows.

=== Pre-bind state information ===
LOG: DisplayName = graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
 (Fully-specified)
LOG: Appbase = C:\Program Files\Microsoft.NET\FrameworkSDK\Samples\Tutorials\resourcesandlocalization\graphic\cs\
LOG: Initial PrivatePath = NULL
LOG: Dynamic Base = NULL
LOG: Cache Base = NULL
LOG: AppName = NULL
Calling assembly : graphicfailtest, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
===

LOG: Processing DEVPATH.
LOG: DEVPATH is not set. Falling through to regular bind.
LOG: Policy not being applied to reference at this time (private, custom, partial, or location-based assembly bind).
LOG: Post-policy reference: graphicfailtest.resources, Version=0.0.0.0, Culture=en-US, PublicKeyToken=null
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.DLL.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources.EXE.
LOG: Attempting download of new URL file:///C:/Program Files/Microsoft.NET/FrameworkSDK/Samples/Tutorials/resourcesandlocalization/graphic/cs/graphicfailtest.resources/graphicfailtest.resources.EXE.
LOG: All probing URLs attempted and failed.
```

### <a name="delete-entries"></a>Eliminar entradas

Para eliminar una entrada del registro:

1. Seleccione la entrada en el visor.

2. Haga clic en el botón **Eliminar entrada**.

Para eliminar todas las entradas del registro:

- Haga clic en el botón **Eliminar todo**.

### <a name="refresh-the-user-interface"></a>Actualizar la interfaz de usuario

- Haga clic en el botón **Actualizar**. Mientras se ejecuta, el visor no detecta automáticamente las entradas nuevas del registro. Debe usar el botón **Actualizar** para mostrarlas.

### <a name="change-the-log-settings"></a>Cambiar la configuración de registro

Haga clic en el botón **Configuración** para abrir el cuadro de diálogo **Configuración de registro**.

### <a name="view-the-about-dialog"></a>Ver el cuadro de diálogo Acerca de

Haga clic en el botón **Acerca de**.

## <a name="binding-logs-for-native-images"></a>Registros de enlaces de las imágenes nativas

De forma predeterminada, Fuslogvw.exe registra las solicitudes de enlace de ensamblado normales. También tiene la opción de registrar los enlaces de ensamblado de las imágenes nativas creadas mediante [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md).

### <a name="log-assembly-binds-for-native-images"></a>Registrar los enlaces de ensamblado de las imágenes nativas

- En el grupo **Categorías de registro**, seleccione el botón de opción **Imágenes nativas**.

El registro siguiente muestra un error producido por una dependencia que no existía cuando se creó la imagen nativa para la aplicación. Si las dependencias en tiempo de ejecución difieren de las dependencias en el momento de la ejecución de Ngen.exe, no se permitirá el enlace a una imagen nativa.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:22:07 PM) ***

The operation failed.
Bind result: hr = 0x80070002. The system cannot find the file specified.

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\App.exe
--- A detailed error log follows.

LOG: Start binding of native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\App.exe.
LOG: Start validating native image App, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency b, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
WRN: Dependency assembly was not found at ngen time, but is found at binding time. Disallow using this native image.
WRN: No matching native image found.
LOG: Bind to native image assembly did not succeed. Use IL image.
```

El registro siguiente muestra un error de enlace a una imagen nativa producido porque la configuración de seguridad del equipo cuando se ejecutó la aplicación era distinta de la configuración de seguridad en el momento en que se creó la imagen nativa.

```output
*** Assembly Binder Log Entry  (12/8/2006 @ 5:29:09 PM) ***

The operation failed.
Bind result: hr = 0x80004005. Unspecified error

Assembly manager loaded from:  E:\Windows\Microsoft.NET\Framework64\v2.0.50727\mscorwks.dll
Running under executable  E:\test\Application101622.exe
--- A detailed error log follows.

LOG: Start binding of native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: IL assembly loaded from E:\test\Application101622.exe.
LOG: Start validating native image Application101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Start validating all the dependencies.
LOG: [Level 1]Start validating native image dependency mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089.
LOG: Dependency evaluation succeeded.
LOG: [Level 1]Start validating IL dependency Dependency101622, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null.
LOG: Dependency evaluation succeeded.
LOG: Validation of dependencies succeeded.
LOG: Start loading all the dependencies into load context.
LOG: Loading of dependencies succeeded.
LOG: Bind to native image succeeded.
Native image has correct version information.
Attempting to use native image E:\Windows\assembly\NativeImages_v2.0.50727_64\Application101622\1ac7fadabec4f72575d807501e9fdc72\Application101622.ni.exe.
Rejecting native image because it failed the security check. The assembly's permissions must have changed since the time it was ngenned, or it is running with a different security context.
Discarding native image.
```

## <a name="the-log-settings-dialog"></a>El cuadro de diálogo Configuración de registro

Puede usar el cuadro de diálogo **Configuración de registro** para realizar las acciones siguientes.

### <a name="to-disable-logging"></a>Para deshabilitar el registro

- Seleccione el botón de opción **Registro deshabilitado**.  Tenga en cuenta que esta opción está seleccionada de forma predeterminada.

### <a name="to-log-assembly-binds-in-exceptions"></a>Para registrar enlaces de ensamblado en excepciones

- Seleccione el botón de opción **Registrar texto de excepciones**. En el texto de excepciones solo se registra la información de registro de Fusion menos detallada. Para ver toda la información, use cualquier otra opción.

  Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.

### <a name="to-log-assembly-bind-failures"></a>Para registrar los errores de enlace de ensamblado

- Seleccione el botón de opción **Registrar errores de enlace en el disco**.

  Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.

### <a name="to-log-all-assembly-binds"></a>Para registrar todos los enlaces de ensamblado

- Seleccione el botón de opción **Registrar todos los enlaces en el disco**.

  Vea la nota Importante referente a los ensamblados que se cargan como dominios neutros.

> [!IMPORTANT]
> Cuando se carga un ensamblado como dominio neutro, por ejemplo, mediante el establecimiento de la propiedad <xref:System.AppDomainSetup.LoaderOptimization%2A> en <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> o <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType>, en algunos casos la activación del registro puede originar pérdidas de memoria. Esto puede suceder si se realiza una entrada de registro al cargar un módulo con dominio neutro en un dominio de aplicación y, posteriormente, se descarga el dominio de aplicación. Puede ocurrir que la entrada de registro no se libere hasta que finalice el proceso. Algunos depuradores activan automáticamente el registro.

### <a name="to-enable-a-custom-log-path"></a>Para habilitar una ruta de acceso de registro personalizada

1. Seleccione el botón de opción **Habilitar ruta de acceso de registro personalizada**.

2. Escriba la ruta de acceso en el cuadro de texto **Ruta de acceso de registro personalizada**.

> [!NOTE]
> El [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) usa la memoria caché de Internet Explorer (IE) para almacenar el registro de enlaces. Debido a daños ocasionales en la memoria caché de IE, a veces el [Visor de registro de enlaces de ensamblados (Fuslogvw.exe)](fuslogvw-exe-assembly-binding-log-viewer.md) deja de mostrar los nuevos registros de enlaces en la ventana de visualización. Como consecuencia de estos daños, la infraestructura de enlaces (Fusion) de .NET no puede escribir en el registro de enlaces ni leerlo. (Este problema no aparece si se usa una ruta de acceso de registro personalizada).  Para corregir los daños y permitir que Fusion vuelva a mostrar los registros de enlaces, borre la memoria caché de IE; para ello, elimine los archivos temporales de Internet en el cuadro de diálogo Opciones de Internet de Internet Explorer.
>
> Si la aplicación no administrada hospeda Common Language Runtime mediante la implementación de las interfaces `IHostAssemblyManager` e `IHostAssemblyStore`, las entradas de registro no pueden almacenarse en la memoria caché de wininet. Para ver las entradas de registro para los host personalizados que implementan estas interfaces, debe especificar otra ruta de acceso de registro.

### <a name="to-enable-logging-for-apps-running-in-the-windows-app-container"></a>Para habilitar el registro para las aplicaciones que se ejecutan en el contenedor de la aplicación de Windows

1. Habilite una ruta de acceso de registro personalizada, tal y como se describe en el procedimiento anterior. De forma predeterminada, las aplicaciones que se ejecutan en el contenedor de la aplicación de Windows tienen acceso limitado al disco duro. El directorio especificado tendrá acceso de lectura y escritura para todas las aplicaciones del contenedor de la aplicación.

2. Seleccione la casilla **Habilitar registro envolvente**.

    > [!NOTE]
    > Este cuadro solo está habilitada en Windows 8 o posterior.

## <a name="see-also"></a>Vea también

- <xref:System.TypeLoadException>
- [Herramientas](index.md)
- [Caché global de ensamblados](../app-domains/gac.md)
- [Cómo el motor en tiempo de ejecución ubica ensamblados](../deployment/how-the-runtime-locates-assemblies.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
