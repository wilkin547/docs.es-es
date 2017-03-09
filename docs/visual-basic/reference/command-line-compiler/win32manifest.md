---
title: "/win32manifest (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/win32manifest (opción del compilador) [Visual Basic]"
  - "win32manifest (opción del compilador) [Visual Basic]"
  - "-win32manifest (opción del compilador) [Visual Basic]"
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# /win32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Identifica un archivo de manifiesto de la aplicación Win32 definido por el usuario para que se incruste en el archivo ejecutable portable \(PE\) de un proyecto.  
  
## Sintaxis  
  
```  
/win32manifest: fileName  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`fileName`|Ruta de acceso del archivo de manifiesto personalizado.|  
  
## Comentarios  
 De forma predeterminada, el compilador de Visual Basic incrusta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de asInvoker.  Crea el manifiesto en la misma carpeta en la que se compila el archivo ejecutable, normalmente la carpeta bin\\Debug o bin\\Release cuando se utiliza Visual Studio.  Si desea proporcionar un manifiesto personalizado, por ejemplo para especificar un nivel de ejecución solicitado de highestAvailable o requireAdministrator, utilice esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
>  Esta opción y la opción [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) son mutuamente excluyentes.  Si intenta utilizar ambas opciones en la misma línea de comandos, obtendrá un error de compilación.  
  
 Una aplicación sin un manifiesto de aplicación que especifique un nivel de ejecución solicitado se someterá a la virtualización de archivos y del Registro bajo la característica Control de cuentas de usuario de Windows Vista.  Para obtener más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visual-studio/deployment/clickonce-deployment-on-windows-vista).  
  
 Su aplicación se someterá a la virtualización si se cumplen las siguientes condiciones:  
  
1.  Utilice la opción `/nowin32manifest` y no proporcione ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos Windows \(.res\) utilizando la opción `/win32resource`.  
  
2.  Proporcione un manifiesto personalizado que no especifique ningún nivel de ejecución solicitado.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] crea un archivo .manifest predeterminado y lo almacena en los directorios de depuración y lanzamiento junto con el archivo ejecutable.  Puede ver o modificar el archivo app.manifest predeterminado haciendo clic en **Ver configuración de UAC** en la pestaña **Aplicación** del Diseñador de proyectos. Para obtener más información, vea [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
 Puede proporcionar el manifiesto de aplicación como paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 mediante la opción `/nowin32manifest`.  Utilice esa misma opción si desea que la aplicación se someta a la virtualización de archivos o del Registro en Windows Vista.  De esta forma, se evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo PE.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador de Visual Basic inserta en un archivo PE.  
  
> [!NOTE]
>  El compilador inserta un nombre de aplicación estándar MyApplication.app en el manifiesto XML.  Ésta es una solución alternativa para habilitar las aplicaciones con el fin de que se ejecuten en Windows Server 2003 Service Pack 3.  
  
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
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/nowin32manifest](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)