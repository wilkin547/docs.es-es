---
description: Opciones del compilador de C# para controlar recursos insertados de Windows en una aplicación dotnet.
title: 'Opciones del compilador de C#: opciones de recursos'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- Win32Resource compiler option [C#]
- Win32Icon compiler option [C#]
- Win32Manifest compiler option [C#]
- NoWin32Manifest compiler option [C#]
- Resources compiler option [C#]
- LinkResources compiler option [C#]
ms.openlocfilehash: fe2da8cae67bc597d2b84a395861a0e4c32c9d72
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482468"
---
# <a name="c-compiler-options-that-specify-resources"></a>Opciones del compilador de C# que especifican recursos

Las opciones siguientes controlan cómo el compilador de C# crea o importa recursos de Win32. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **Win32Resource** / `-win32res`: se especifica un archivo de recursos (.res) de Win32.
- **Win32Icon** / `-win32icon`: se hace referencia a los metadatos de los archivos de ensamblado especificados.
- **Win32Manifest** / `-win32manifest`:se especifica un archivo de manifiesto (.xml) de Win32.
- **NoWin32Manifest** / `-nowin32manifest`: no se incluye el manifiesto de Win32 predeterminado.
- **Resources** / `-resource`: se inserta el recurso especificado (forma abreviada: /res).
- **LinkResources** / `-linkresources`:se vincula el recurso especificado a este ensamblado.

## <a name="win32resource"></a>Win32Resource

La opción **Win32Resource** inserta un recurso de Win32 en el archivo de salida.

```xml
<Win32Resource>filename</Win32Resource>
```

`filename` es el archivo de recursos que se quiere agregar al archivo de salida. Un recurso de Win32 puede contener información de versión o de mapa de bits (icono) que ayudaría a identificar la aplicación en el Explorador de archivos. Si no especifica esta opción, el compilador generará información de versión en función de la versión del ensamblado.

## <a name="win32icon"></a>Win32Icon

La opción **Win32Icon** inserta un archivo .ico en el archivo de salida, lo que proporciona al archivo de salida la apariencia esperada en el Explorador de archivos.
  
```xml
<Win32Icon>filename</Win32Icon>
```

`filename` es el archivo *.ico* que quiere agregar al archivo de salida. Se puede crear un archivo *.ico* con el [Compilador de recursos](/windows/desktop/menurc/resource-compiler). El Compilador de recursos se invoca al compilar un programa de Visual C++ y se crea un archivo *.ico* a partir del archivo *.rc*.

## <a name="win32manifest"></a>Win32Manifest

Use la opción **Win32Manifest** para especificar un archivo de manifiesto de aplicación Win32 definido por el usuario que se va a insertar en un archivo portable ejecutable (PE) del proyecto.

```xml
<Win32Manifest>filename</Win32Manifest>
```

`filename` es el nombre y la ubicación del archivo de manifiesto personalizado. De forma predeterminada, el compilador de C# inserta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de "asInvoker". Crea el manifiesto en la misma carpeta en la que se compila el ejecutable. Si quiere proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de "highestAvailable" o "requireAdministrator", use esta opción para especificar el nombre del archivo.

> [!NOTE]
> Esta opción y **Win32Resources** son mutuamente excluyentes. Si intenta usar ambas en la misma línea de comandos, obtendrá un error de compilación.

Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows. Para más información, vea [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview) (Control de cuentas de usuario).

La aplicación estará sujeta a virtualización si se cumple cualquiera de estas condiciones:
  
- Se usa la opción **NoWin32Manifest** y no se proporciona ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows ( *.res*) mediante la opción **Win32Resource**.
- Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.

Visual Studio crea un archivo *.manifest* predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable. Puede agregar un manifiesto personalizado si crea uno en cualquier editor de texto y luego lo agrega al proyecto. O bien, puede hacer clic con el botón derecho en el icono **Proyecto** del **Explorador de soluciones**, seleccionar **Agregar nuevo elemento** y luego **Archivo de manifiesto de aplicación**. Después de haber agregado el archivo de manifiesto nuevo o existente, aparecerá en la lista desplegable **Manifiesto**. Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).

Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 con la opción **NoWin32Manifest**. Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista.
  
## <a name="nowin32manifest"></a>NoWin32Manifest

Use la opción **NoWin32Manifest** para indicar al compilador que no inserte ningún manifiesto de aplicación en el archivo ejecutable.

```xml  
<NoWin32Manifest />
```

Cuando se use esta opción, la aplicación estará sujeta a la virtualización en Windows Vista a menos que proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.

En Visual Studio, defina esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**. Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).

## <a name="resources"></a>Recursos

Inserta el recurso especificado en el archivo de salida.

```xml
<Resources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</Resources>
```

`filename` es el archivo de recursos de .NET que quiere insertar en el archivo de salida. `identifier` (opcional) es el nombre lógico del recurso, que se usa para cargarlo. El valor predeterminado es el nombre del archivo. `accessibility-modifier` (opcional) es la accesibilidad del recurso: pública o privada. El valor predeterminado es public. De manera predeterminada, los recursos son públicos en el ensamblado cuando se crean mediante el compilador de C#. Para que sean privados, especifique el modificador de accesibilidad `private`. No se permite ninguna otra accesibilidad distinta de `public` o `private`. Si `filename` es un archivo de recursos de .NET creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede acceder a él con miembros del espacio de nombres <xref:System.Resources>. Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución. El orden de los recursos en el archivo de salida se determina a partir del orden especificado en el archivo del proyecto.  
  
## <a name="linkresources"></a>LinkResources

Crea un vínculo a un recurso de .NET en el archivo de salida. El archivo de recursos no se agrega al archivo de salida. **LinkResources** difiere de la opción **Resource**, que sí inserta un archivo de recursos en el archivo de salida.

```xml
<LinkResources Include=filename>
  <LogicalName>identifier</LogicalName>
  <Access>accessibility-modifier</Access>
</LinkResources>
```

`filename` es el archivo de recursos de .NET con el que quiere crear un vínculo desde el ensamblado. `identifier` (opcional) es el nombre lógico del recurso, que se usa para cargarlo. El valor predeterminado es el nombre del archivo. `accessibility-modifier` (opcional) es la accesibilidad del recurso: pública o privada. El valor predeterminado es public. De manera predeterminada, los recursos vinculados son públicos en el ensamblado cuando se crean con el compilador de C#. Para que sean privados, especifique el modificador de accesibilidad `private`. No se permite ningún otro modificador distinto de `public` o `private`. Si `filename` es un archivo de recursos de .NET creado, por ejemplo, con [Resgen.exe](../../../framework/tools/resgen-exe-resource-file-generator.md) o en el entorno de desarrollo, se puede acceder a él con miembros del espacio de nombres <xref:System.Resources>. Para obtener más información, vea <xref:System.Resources.ResourceManager?displayProperty=nameWithType>. Para todos los demás recursos, use los métodos `GetManifestResource` de la clase <xref:System.Reflection.Assembly> para tener acceso al recurso en tiempo de ejecución. El archivo especificado en `filename` puede tener cualquier formato. Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado. También es posible realizar lo mismo en Assembly Linker. Para obtener más información, vea [Al.exe (Assembly Linker)](../../../framework/tools/al-exe-assembly-linker.md) y [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../framework/app-domains/working-with-assemblies-and-the-gac.md).
