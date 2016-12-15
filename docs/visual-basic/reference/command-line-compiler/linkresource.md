---
title: "/linkresource (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/linkres (opción del compilador) [Visual Basic]"
  - "/linkresource (opción del compilador) [Visual Basic]"
  - "linkres (opción del compilador) [Visual Basic]"
  - "-linkres (opción del compilador) [Visual Basic]"
  - "linkresource (opción del compilador) [Visual Basic]"
  - "-linkresource (opción del compilador) [Visual Basic]"
ms.assetid: cf4dcad8-17b7-404c-9184-29358aa05b15
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /linkresource (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Crea un vínculo a un recurso administrado.  
  
## Sintaxis  
  
```  
/linkresource:filename[,identifier[,public|private]]  
' -or-  
/linkres:filename[,identifier[,public|private]]  
```  
  
## Argumentos  
 `filename`  
 Obligatorio.  Archivo de recursos que se va a vincular al ensamblado.  Si el nombre de archivo contiene un espacio, inclúyalo entre comillas \(""\).  
  
 `identifier`  
 Opcional.  El nombre lógico para el recurso.  El nombre que se utiliza para cargar el recurso.  El valor predeterminado es el nombre del archivo.  De manera opcional, se puede especificar si el archivo es público o privado en el manifiesto del ensamblado, por ejemplo: `/linkres:filename.res,myname.res,public`.  De manera predeterminada, `filename` es público en el ensamblado.  
  
## Comentarios  
 La opción `/linkresource` no incluye el archivo de recursos en el archivo de salida; para incluirlo utilice `/resource`.  
  
 La opción  `/linkresource` requiere una de las opciones de `/target` distinta de `/target:module`.  
  
 Si `filename` es un archivo de recursos de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] creado, por ejemplo, con [Resgen.exe \(Resource File Generator\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) o en el entorno de desarrollo, se puede tener acceso a él con miembros del espacio de nombres <xref:System.Resources>.  \(Para obtener más información, vea <xref:System.Resources.ResourceManager>\). Para tener acceso a los demás recursos en tiempo de ejecución, utilice los métodos que empiezan por `GetManifestResource` de la clase <xref:System.Reflection.Assembly>.  
  
 El nombre de archivo puede utilizar cualquier formato de archivo.  Por ejemplo, se puede hacer que una DLL nativa forme parte de un ensamblado para que se pueda instalar en la caché global de ensamblados y sea accesible desde código administrado del ensamblado.  
  
 La forma corta de `/linkresource` es `/linkres`.  
  
> [!NOTE]
>  La opción `/linkresource` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 El código siguiente compila `In.vb` y lo vincula al archivo de recursos `Rf.resource`.  
  
```  
vbc /linkresource:rf.resource in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/resource](../../../visual-basic/reference/command-line-compiler/resource.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)