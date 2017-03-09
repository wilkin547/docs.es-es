---
title: "/keycontainer | Microsoft Docs"
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
  - "/keycontainer (opción del compilador) [Visual Basic]"
  - "keycontainer (opción del compilador) [Visual Basic]"
  - "-keycontainer (opción del compilador) [Visual Basic]"
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /keycontainer
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica un nombre de contenedor de claves para un par de claves con el fin de asignar un nombre seguro a un ensamblado.  
  
## Sintaxis  
  
```  
/keycontainer:container  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`container`|Obligatorio.  Archivo de contenedor que incluye la clave.  Escriba el nombre de archivo entre comillas \(" "\) si contiene espacios.|  
  
## Comentarios  
 El compilador crea el componente de uso compartido insertando una clave pública en el manifiesto del ensamblado y firmando el ensamblado final con la clave privada.  Para generar un archivo de clave, escriba `sn -k``file` en la línea de comandos.  La opción `-i`  instala el par de claves en un contenedor.  Para obtener más información, vea [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
 Si se compila con la opción `/target:module`, el nombre del archivo de clave se mantiene en el módulo y se incorpora en el ensamblado que se crea al compilar un ensamblado con la opción [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 También puede especificar esta opción como un atributo personalizado \(<xref:System.Reflection.AssemblyKeyNameAttribute>\) en el código fuente de cualquier módulo de lenguaje intermedio de Microsoft \(MSIL\).  
  
 También puede pasar la información de cifrado al compilador mediante [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).  Utilice [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) para firmar un ensamblado de forma parcial.  
  
 Vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) para obtener más información sobre cómo firmar un ensamblado.  
  
> [!NOTE]
>  La opción `/keycontainer` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila el archivo de código fuente `Input.vb` y especifica un contenedor de claves.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## Vea también  
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)