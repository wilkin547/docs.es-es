---
title: "/delaysign | Microsoft Docs"
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
  - "/delaysign (opción del compilador) [Visual Basic]"
  - "delaysign (opción del compilador) [Visual Basic]"
  - "-delaysign (opción del compilador) [Visual Basic]"
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /delaysign
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica si el ensamblado estará firmado total o parcialmente.  
  
## Sintaxis  
  
```  
/delaysign[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  Utilice `/delaysign-` para firmar completamente un ensamblado.  Utilice `/delaysign+` si desea colocar la clave pública en el ensamblado y reservar espacio para el hash firmado.  El valor predeterminado es `/delaysign-`.  
  
## Comentarios  
 La opción `/delaysign` no tiene ningún efecto a menos que se utilice con [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Cuando se solicita un ensamblado con firma completa, el compilador calcula el hash del archivo que contiene el manifiesto \(metadatos de ensamblado\) y firma el hash con la clave privada.  La firma digital resultante se almacena en el archivo que contiene el manifiesto.  Cuando se firma un ensamblado de forma retardada, el compilador no calcula ni almacena la firma, pero reserva espacio en el archivo para poder agregar la firma más tarde.  
  
 Por ejemplo, al utilizar `/delaysign+`, un desarrollador de una organización distribuye versiones de prueba sin firma de un ensamblado que quienes realizan pruebas pueden utilizar y registrar con la Caché global de ensamblados.  Cuando el trabajo en el ensamblado ha finalizado, la persona responsable de la clave privada de la organización puede firmar totalmente el ensamblado.  Esta división de funciones protege la clave privada de la organización del descubrimiento y permite a todos los desarrolladores trabajar en los ensamblados.  
  
 Vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) para obtener más información sobre cómo firmar un ensamblado.  
  
### Para establecer \/delaysign en el entorno de desarrollo integrado \(IDE\) de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Firma**.  
  
3.  Establezca el valor en el cuadro **Retrasar firma sólo**.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)