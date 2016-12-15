---
title: "/reference (Visual Basic) | Microsoft Docs"
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
  - "/r (opción del compilador) [Visual Basic]"
  - "/reference (opción del compilador) [Visual Basic]"
  - "r (opción del compilador) [Visual Basic]"
  - "-r (opción del compilador) [Visual Basic]"
  - "reference (opción del compilador) [Visual Basic]"
  - "-reference (opción del compilador) [Visual Basic]"
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /reference (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador facilite la información de tipos presente en los ensamblados especificados al proyecto que se compila actualmente.  
  
## Sintaxis  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`fileList`|Obligatorio.  Lista delimitada por comas de nombres de archivos de ensamblado.  Si el nombre de archivo contiene un espacio, incluya el nombre entre comillas.|  
  
## Comentarios  
 Los archivos importados deben contener metadatos de ensamblado.  Fuera del ensamblado sólo serán visibles los tipos públicos.  La opción [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa metadatos de un módulo.  
  
 Si se hace referencia a un ensamblado \(Ensamblado A\) que, a su vez, hace referencia a otro ensamblado \(Ensamblado B\), se deberá hacer referencia al ensamblado B si:  
  
-   Un tipo utilizado en el Ensamblado A hereda de un tipo o implementa una interfaz del Ensamblado B.  
  
-   Se invoca un campo, una propiedad, un evento o un método que tiene un tipo de valor devuelto o un tipo de parámetro del Ensamblado B.  
  
 Utilice [\/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) para especificar el directorio en el que se encuentran una o varias de las referencias de ensamblados.  
  
 Para que el compilador reconozca un tipo en un ensamblado \(no un módulo\), es preciso obligarlo a resolver el tipo.  Un ejemplo de cómo se puede hacer esto es definir una instancia del tipo.  Hay otras formas de resolver nombres de tipos en un ensamblado para el compilador.  Por ejemplo, si hereda de un tipo de un ensamblado, el compilador pasará a conocer el nombre del tipo.  
  
 El archivo de respuesta Vbc.rsp, que hace referencia a los ensamblados utilizados comúnmente en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], es el predeterminado.  Utilice `/noconfig` si no desea que el compilador utilice Vbc.rsp.  
  
 La forma corta de `/reference`  es `/r`.  
  
## Ejemplo  
 El código siguiente compila el archivo de código fuente I`nput.vb` e importa ensamblados de M`etad1.dll` y M`etad2.dll` para generar O`ut.exe`.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)