---
title: -win32manifest
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cef1e6c19e7fdd6fc9f42c8fc36008314ea80a80
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349129"
---
# <a name="-win32manifest-visual-basic"></a>-win32manifest (Visual Basic)
Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileName`|Ruta de acceso al archivo de manifiesto personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador de Visual Basic inserta de forma predeterminada un manifiesto de aplicación que especifica un nivel de ejecución solicitado de asInvoker. Crea el manifiesto en la misma carpeta en la que se ha compilado el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se usa Visual Studio. Si quiere proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de highestAvailable o requireAdministrator, use esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
> Esta opción y [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) son mutuamente excluyentes. Si intenta usar ambas en la misma línea de comandos, obtendrá un error de compilación.  
  
 Una aplicación sin manifiesto de aplicación que especifique un nivel de ejecución solicitado estará sujeta a virtualización de archivos y Registro conforme a la característica Control de cuentas de usuario de Windows Vista. Para más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 La aplicación estará sujeta a virtualización si se cumple cualquiera de las siguientes condiciones:  
  
1. Se usa la opción `-nowin32manifest` y no se proporciona ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (.res) con la opción `-win32resource`.  
  
2. Se proporciona un manifiesto personalizado que no especifica un nivel de ejecución solicitado.  
  
 Visual Studio crea un archivo de manifiesto predeterminado y lo almacena en los directorios de depuración y versión junto con el archivo ejecutable. Para ver o editar el archivo app.manifest predeterminado, haga clic en **Ver configuración de UAC** en la pestaña **Aplicación** del Diseñador de proyectos. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Puede proporcionar el manifiesto de aplicación como un paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 con la opción `-nowin32manifest`. Use esa misma opción si quiere que la aplicación esté sujeta a virtualización de archivos y Registro en Windows Vista. Esto evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo PE.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra el manifiesto predeterminado que el compilador de Visual Basic inserta en un archivo PE.  
  
> [!NOTE]
> El compilador inserta un nombre de aplicación estándar MyApplication.app en el archivo XML de manifiesto. Se trata de una solución alternativa para permitir que las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.  
  
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

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
