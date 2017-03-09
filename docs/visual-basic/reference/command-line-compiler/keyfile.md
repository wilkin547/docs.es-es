---
title: "/keyfile | Microsoft Docs"
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
  - "/keyfile (opción del compilador) [Visual Basic]"
  - "keyfile (opción del compilador) [Visual Basic]"
  - "-keyfile (opción del compilador) [Visual Basic]"
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /keyfile
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica un archivo que contiene una clave o un par de claves a fin de asignar un nombre seguro a un ensamblado.  
  
## Sintaxis  
  
```  
/keyfile:file  
```  
  
## Argumentos  
 `file`  
 Obligatorio.  Archivo que contiene la clave.  Si el nombre de archivo contiene un espacio, inclúyalo entre comillas \(""\).  
  
## Comentarios  
 El compilador inserta la clave pública en el manifiesto del ensamblado y firma el ensamblado final con la clave privada.  Para generar un archivo de clave, escriba `sn -k file` en la línea de comandos.  Para obtener más información, vea [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 Si se compila con la opción `/target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede pasar la información de cifrado al compilador mediante [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  Utilice [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar un ensamblado de forma parcial.  
  
 También puede especificar esta opción como un atributo personalizado \(<xref:System.Reflection.AssemblyKeyFileAttribute>\) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft.  
  
 Si se especifican `/keyfile` y [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) \(ya sea mediante una opción de línea de comandos o mediante un atributo personalizado\) en la misma compilación, el compilador intenta utilizar primero el contenedor de clave.  Si el intento tiene éxito, el ensamblado se firmará con la información del contenedor de claves.  Si el compilador no encuentra el contenedor de clave, prueba con el archivo especificado en `/keyfile`.  Si el intento tiene éxito, el ensamblado se firma con la información contenida en el archivo de clave, y esta información se instalará en el contenedor de claves \(de forma similar a `sn -i`\), de modo que, en la siguiente compilación, el contenedor de claves ya será válido.  
  
 Tenga en cuenta que es posible que un archivo de claves contenga sólo la clave pública.  
  
 Vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  La opción `/keyfile` no está disponible en el entorno de desarrollo de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]; solo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea de código compila el archivo de código fuente `Input.vb` y especifica un archivo de clave.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## Vea también  
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)