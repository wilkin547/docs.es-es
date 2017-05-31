---
title: "Codificación de archivos (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- character encodings
- files, encoding
- Unicode, file encoding
- file encoding
ms.assetid: ea2c5f5f-bbb1-4150-9928-b9951fa6bc57
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d59312951429780990e9cc048e3ad0671b81d8ae
ms.contentlocale: es-es
ms.lasthandoff: 04/12/2017

---
# <a name="file-encodings-visual-basic"></a>Codificación de archivos (Visual Basic)
Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto. Una codificación puede ser preferible sobre otra por lo que se refiere a los caracteres del lenguaje que puede o no controlar, aunque normalmente se prefiere Unicode.  
  
 Cuando se leen o escriben archivos, la correspondencia incorrecta de las codificaciones de archivo puede producir excepciones o resultados incorrectos.  
  
## <a name="types-of-encodings"></a>Tipos de codificaciones  
 Unicode es la codificación preferida al trabajar con archivos. Unicode es un estándar mundial de codificación de caracteres que usa valores de código de 16 bits para representar todos los caracteres que se usan en la informática moderna, e incluye símbolos técnicos y caracteres especiales que se usan en publicaciones.  
  
 Los estándares de codificación de caracteres anteriores constaban de juegos de caracteres tradicionales, como el juego de caracteres ANSI de Windows que usa valores de código de 8 bits, o combinaciones de valores de 8 bits, para representar los caracteres que se usan en un idioma o región geográfica específicos.  
  
## <a name="encoding-class"></a>Clase Encoding  
 La clase <xref:System.Text.Encoding> representa una codificación de caracteres. En esta tabla se muestra el tipo de codificaciones disponibles y se describe cada uno.  
  
|Nombre|Descripción|
|---|---|    
|<xref:System.Text.ASCIIEncoding>|Representa una codificación de caracteres ASCII de caracteres Unicode.|  
|<xref:System.Text.UnicodeEncoding>|Representa una codificación UTF-16 de caracteres Unicode.|  
|<xref:System.Text.UTF32Encoding>|Representa una codificación UTF-32 de caracteres Unicode.|  
|<xref:System.Text.UTF7Encoding>|Representa una codificación UTF-7 de caracteres Unicode.|  
|<xref:System.Text.UTF8Encoding>|Representa una codificación UTF-8 de caracteres Unicode.|  
  
## <a name="see-also"></a>Vea también  
 [Reading from Files in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  (Leer archivos en Visual Basic)  
 [Escritura en archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
