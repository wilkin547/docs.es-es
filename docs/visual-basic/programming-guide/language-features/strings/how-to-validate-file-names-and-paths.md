---
title: "C&#243;mo: Validar rutas de acceso y nombres de archivo en Visual Basic | Microsoft Docs"
ms.custom: ""
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
  - "valores booleanos"
  - "nombres de archivo, validar"
  - "rutas de acceso, validar"
  - "cadenas [Visual Basic], validar"
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# C&#243;mo: Validar rutas de acceso y nombres de archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este ejemplo devuelve un valor `Boolean` que indica si una cadena representa un nombre de archivo o ruta de acceso.  La validación comprueba si el nombre contiene caracteres que el sistema de archivos no permite.  
  
## Ejemplo  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 Este ejemplo no comprueba si el nombre tiene signos de punto y coma en posiciones incorrectas, si hay directorios sin nombre o si la longitud del nombre supera la longitud máxima definida por el sistema.  Tampoco comprueba si la aplicación dispone de permiso para tener acceso al recurso del sistema de archivos con el nombre especificado.  
  
## Vea también  
 <xref:System.IO.Path.GetInvalidPathChars%2A>   
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)