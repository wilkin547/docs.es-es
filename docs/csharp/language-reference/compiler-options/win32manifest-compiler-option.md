---
description: -win32manifest (Opciones del compilador de C#)
title: -win32manifest (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
ms.openlocfilehash: 4ce4033323eb938caff1d769198ca69782b470ab
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140833"
---
# <a name="-win32manifest-c-compiler-options"></a>-win32manifest (Opciones del compilador de C#)
Use la opción **-win32manifest** para identificar un archivo de manifiesto de aplicación Win32 definido por el usuario que se va a incluir en un archivo portable ejecutable (PE) del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32manifest: filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 Nombre y ubicación del archivo de manifiesto personalizado.  
  
## <a name="remarks"></a>Observaciones  
 De forma predeterminada, el compilador de Visual C# inserta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de "asInvoker". Crea el manifiesto en la misma carpeta en la que se ha compilado el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se usa Visual Studio. Si quiere proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de "highestAvailable" o "requireAdministrator", use esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
> Esta opción y [-win32res (Opciones del compilador de C#)](./win32res-compiler-option.md) son mutuamente excluyentes. Si intenta usar ambas en la misma línea de comandos, obtendrá un error de compilación.  
  
 Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows. Para más información, vea [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview) (Control de cuentas de usuario).  
  
 La aplicación estará sujeta a virtualización si se cumple cualquiera de estas condiciones:  
  
- Se usa la opción **-nowin32manifest** y no se proporciona ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (.res) mediante la opción **-win32res**.  
  
- Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.  
  
 Visual Studio crea un archivo de manifiesto predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable. Puede agregar un manifiesto personalizado si crea uno en cualquier editor de texto y luego lo agrega al proyecto. También puede hacer clic con el botón derecho en el icono **Proyecto** del **Explorador de soluciones**, hacer clic en **Agregar nuevo elemento** y luego en **Archivo de manifiesto de aplicación**. Después de haber agregado el archivo de manifiesto nuevo o existente, aparecerá en la lista desplegable **Manifiesto**. Para más información, vea [Página de aplicación, Diseñador de proyectos (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).  
  
 Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 mediante la opción [-nowin32manifest (Opciones del compilador de C#)](./nowin32manifest-compiler-option.md). Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista. Esto evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo portable ejecutable (PE).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador de Visual C# inserta en un archivo PE.  
  
> [!NOTE]
> El compilador inserta un nombre de aplicación estándar "MyApplication.app" en el archivo xml. Se trata de una solución alternativa para permitir que las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [-nowin32manifest (Opciones del compilador de C#)](./nowin32manifest-compiler-option.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
