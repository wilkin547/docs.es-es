---
title: "/win32manifest (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/win32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/win32manifest compiler option [C#]"
  - "win32manifest compiler option [C#]"
  - "-win32manifest compiler option [C#]"
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /win32manifest (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utilice la opción **\/win32manifest** para especificar que un archivo de manifiesto de la aplicación Win32 definido por el usuario se incruste en el archivo portable ejecutable \(PE\) de un proyecto.  
  
## Sintaxis  
  
```  
/win32manifest: filename  
```  
  
## Argumentos  
 `filename`  
 El nombre y la ubicación del archivo de manifiesto personalizado.  
  
## Comentarios  
 De forma predeterminada, el compilador de [!INCLUDE[csharp_current_short](../../../csharp/language-reference/compiler-options/includes/csharp_current_short_md.md)] incrusta un manifiesto de aplicación que especifica un nivel de ejecución solicitado de "asInvoker". Alice crea el manifiesto en la misma carpeta en la que se compila la aplicación ejecutable, normalmente la carpeta de bin\\Debug o de bin\\Release cuando se usa Visual Studio.  Si desea proporcionar un manifiesto personalizado, por ejemplo para especificar una ejecución solicitada level de “highestAvailable” o “requireAdministrator”, utilice esta opción para especificar el nombre del archivo.  
  
> [!NOTE]
>  Esta opción y la opción [\/win32res \(Import a Win32 Resource File\)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) son mutuamente excluyentes.  Si intenta utilizar ambas opciones en la misma línea de comandos obtendrá un error de compilación.  
  
 Una aplicación sin un manifiesto de aplicación que especifique un nivel de ejecución solicitado se someterá a la virtualización de archivos y del Registro bajo la característica Control de cuentas de usuario de Windows Vista.  Para obtener más información sobre la virtualización, vea [El caso de desarrollador de Windows Vista: Requisitos de desarrollo de aplicaciones de Windows Vista para el Control de cuentas de usuario \(UAC\)](http://go.microsoft.com/fwlink/?LinkId=95452).  
  
 Su aplicación se someterá a la virtualización si se cumple cualquiera de estas condiciones:  
  
-   Utilice la opción **\/nowin32manifest** y no proporcione ningún manifiesto en un paso de compilación posterior o como parte de un archivo de recursos Windows \(.res\) utilizando la opción **\/win32res**.  
  
-   Proporcione un manifiesto personalizado que no especifique ningún nivel de ejecución solicitado.  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] crea un archivo .manifest predeterminado y lo almacena en los directorios de depuración y lanzamiento junto con el archivo ejecutable.  Para agregar un manifiesto personalizado, cree uno en cualquier editor de texto y agregue el archivo al proyecto a continuación.  Como alternativa, puede hacer clic con el botón secundario en el icono **Proyecto** del **Explorador de soluciones**, hacer clic en **Agregar nuevo elemento** y, a continuación, en **Archivo de manifiesto de aplicación**.  Después de haber agregado el archivo de manifiesto nuevo o existente, éste aparecerá en la lista desplegable **Manifiesto**.  Para obtener más información, vea [Página de aplicación, Diseñador de proyectos \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Puede proporcionar el manifiesto de aplicación como paso personalizado posterior a la compilación o como parte de un archivo de recursos Win32 mediante la opción [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md).  Utilice esa misma opción si desea que la aplicación se someta a la virtualización de archivos o del Registro en Windows Vista.  De esta forma se evitará que el compilador cree e incruste un manifiesto predeterminado en el archivo portable ejecutable \(PE\).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra el manifiesto predeterminado que el compilador de Visual C\# inserta en un archivo PE.  
  
> [!NOTE]
>  El compilador inserta un nombre de aplicación estándar "MyApplication.app" en el archivo xml.  Ésta es una solución alternativa para habilitar las aplicaciones con el fin de que se ejecuten en Windows Server 2003 Service Pack 3.  
  
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
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/nowin32manifest \(No Win32 Manifest\)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)