---
title: "/baseaddress | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/baseaddress"
  - "baseaddress"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/baseaddress (opción del compilador) [Visual Basic]"
  - "baseaddress (opción del compilador) [Visual Basic]"
  - "-baseaddress (opción del compilador) [Visual Basic]"
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /baseaddress
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## Sintaxis  
  
```  
/baseaddress:address  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`address`|Obligatorio.  Dirección base para el archivo DLL.  Esta dirección debe especificarse en forma de número hexadecimal.|  
  
## Comentarios  
 La dirección base predeterminada para un archivo DLL la establece [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  
  
 Tenga en cuenta que se redondeará la palabra de orden inferior de esta dirección.  Por ejemplo, si se especifica 0x11110001, quedará redondeada como 0x11110000.  
  
 Para completar el proceso de firma de un archivo DLL, utilice la opción `–R` de la herramienta de nombres seguros \(Sn.exe\).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
||  
|-|  
|Para establecer \/baseaddress en el entorno de desarrollo integrado de Visual Studio|  
|1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la ficha **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el cuadro **Dirección base del archivo DLL:**. **Note:**      El cuadro **Dirección base del archivo DLL:** es de sólo lectura a menos que el destino sea un archivo DLL.|  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)