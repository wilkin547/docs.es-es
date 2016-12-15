---
title: "Codificaci&#243;n de archivos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "codificaciones de caracteres"
  - "codificación de archivos"
  - "archivos, codificar"
  - "Unicode, codificación de archivos"
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Codificaci&#243;n de archivos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Las codificaciones de archivos, también conocidas como codificaciones de caracteres, especifican cómo se representan los caracteres cuando se procesa texto.  Una codificación puede ser preferible sobre otra por lo que se refiere a los caracteres del lenguaje que puede o no controlar, aunque normalmente se prefiere Unicode.  
  
 Cuando se leen o escriben archivos, la correspondencia incorrecta de las codificaciones de archivo puede producir excepciones o resultados incorrectos.  
  
## Tipos de codificaciones  
 Unicode es la codificación preferida al trabajar con archivos.  Unicode es un estándar mundial de codificación de caracteres que utiliza valores de código de 16 bits para representar todos los caracteres que se utilizan en la informática moderna, e incluye símbolos técnicos y caracteres especiales que se utilizan en publicaciones.  
  
 Los estándares de codificación de caracteres anteriores constaban de juegos de caracteres tradicionales, como el juego de caracteres ANSI de Windows que utiliza valores de código de 8 bits, o combinaciones de valores de 8 bits, para representar los caracteres que se utilizan en un idioma o región geográfica específicos.  
  
## Clase Encoding  
 La clase <xref:System.Text.Encoding> representa una codificación de caracteres.  En esta tabla se muestra el tipo de codificaciones disponibles y se describe cada uno.  
  
|||  
|-|-|  
|Name|Descripción|  
|<xref:System.Text.ASCIIEncoding>|Representa una codificación en caracteres ASCII de caracteres Unicode.|  
|<xref:System.Text.UnicodeEncoding>|Representa una codificación UTF\-16 de caracteres Unicode.|  
|<xref:System.Text.UTF32Encoding>|Representa una codificación UTF\-32 de caracteres Unicode.|  
|<xref:System.Text.UTF7Encoding>|Representa una codificación UTF\-7 de caracteres Unicode.|  
|<xref:System.Text.UTF8Encoding>|Representa una codificación UTF\-8 de caracteres Unicode.|  
  
## Vea también  
 [Leer archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Escribir en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)