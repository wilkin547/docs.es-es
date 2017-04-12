---
title: /win32manifest (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b07d5816e5bb80a95e608fa7214a2db48ebac0dc
ms.lasthandoff: 03/13/2017

---
# <a name="win32manifest-visual-basic"></a>/win32manifest (Visual Basic)
Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario que se va a insertar en un archivo ejecutable portable (PE) del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`fileName`|La ruta de acceso del archivo de manifiesto personalizado.|  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, el compilador de Visual Basic incrusta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de asInvoker. Crea el manifiesto en la misma carpeta en la que se genera el archivo ejecutable, normalmente la carpeta bin\Debug o bin\Release cuando se utiliza Visual Studio. Si desea proporcionar un manifiesto personalizado, por ejemplo, para especificar un nivel de ejecución solicitado de highestAvailable o requireAdministrator, utilice esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
>  Esta opción y la [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) opción son mutuamente excluyentes. Si intenta utilizar ambas opciones en la misma línea de comandos, obtendrá un error de compilación.  
  
 Una aplicación que no tiene ninguna aplicación manifiesto que especifica que un nivel de ejecución solicitado se someterá a la virtualización de archivos y del registro bajo la característica Control de cuentas de usuario en Windows Vista. Para obtener más información acerca de la virtualización, vea [la implementación de ClickOnce en Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).  
  
 La aplicación se someterá a la virtualización si se cumple alguna de las condiciones siguientes:  
  
1.  Utiliza la `/nowin32manifest` opción y no proporciona un manifiesto en un paso de compilación posterior o como parte de un archivo de recursos de Windows (. res) utilizando la `/win32resource` opción.  
  
2.  Debe proporcionar un manifiesto personalizado que no especifique un nivel de ejecución solicitado.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]crea un archivo .manifest predeterminado y lo almacena en los directorios de depuración y lanzamiento junto con el archivo ejecutable. Puede ver o editar el archivo app.manifest predeterminado haciendo clic en **ver configuración de UAC** en el **aplicación** ficha en el Diseñador de proyectos. Para obtener más información, consulte [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
 Puede proporcionar el manifiesto de aplicación como paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 mediante la `/nowin32manifest` opción. Utilice esa misma opción si desea que la aplicación sometida a la virtualización de archivos o del registro en Windows Vista. Esto evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo PE.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador de Visual Basic inserta en un archivo PE.  
  
> [!NOTE]
>  El compilador inserta un nombre de aplicación estándar MyApplication.app en el manifiesto XML. Se trata de una solución alternativa para habilitar las aplicaciones se ejecuten en Windows Server 2003 Service Pack 3.  
  
```  
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
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
