---
title: "/resource (Visual Basic) | Microsoft Docs"
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
  - "/res (opción del compilador) [Visual Basic]"
  - "/resource (opción del compilador) [Visual Basic]"
  - "res (opción del compilador) [Visual Basic]"
  - "-res (opción del compilador) [Visual Basic]"
  - "resource (opción del compilador) [Visual Basic]"
  - "-resource (opción del compilador) [Visual Basic]"
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /resource (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Incrusta un recurso administrado en un ensamblado.  
  
## Sintaxis  
  
```  
/resource:filename[,identifier[,public|private]]  
' -or-  
/res:filename[,identifier[,public|private]]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`filename`|Obligatorio.  El nombre del archivo de recursos que se desea incrustar en el archivo de salida.  De manera predeterminada, `filename` es público en el ensamblado.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.|  
|`identifier`|Opcional.  Nombre lógico del recurso; el nombre usado para cargar el recurso.  El valor predeterminado es el nombre del archivo.  De manera opcional, se puede especificar si el recurso es público o privado en el manifiesto del ensamblado, como en el caso siguiente: `/res:``filename.res`,`myname.res`,`public`|  
  
## Comentarios  
 Utilice la opción `/linkresource` para vincular un recurso a un ensamblado sin incluir el archivo de recursos en el archivo de salida.  
  
 Si `filename` es un archivo de recursos de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] creado, por ejemplo, con [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) o en el entorno de desarrollo, se puede tener acceso a él con miembros del espacio de nombres <xref:System.Resources> \(vea <xref:System.Resources.ResourceManager> para obtener más información\).  Para tener acceso a los demás recursos en tiempo de ejecución, utilice uno de los métodos siguientes: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A>, <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> o <xref:System.Reflection.Assembly.GetManifestResourceStream%2A>.  
  
 La forma corta de `/resource`  es `/res`.  
  
 Para obtener información acerca de cómo establecer `/resource` en el IDE de Visual Studio, consulte [Administrar los recursos de la aplicación \(.NET\)](/visual-studio/ide/managing-application-resources-dotnet).  
  
## Ejemplo  
 El código siguiente compila `In.vb` y asocia el archivo de recursos `Rf.resource`.  
  
```  
vbc /res:rf.resource in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md)   
 [\/linkresource](../../../visual-basic/reference/command-line-compiler/linkresource.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)