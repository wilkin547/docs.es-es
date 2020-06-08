---
title: 'Solución de problemas: Leer y escribir en archivos de texto'
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting file I/O
- writing text to files [Visual Basic], troubleshooting
- troubleshooting Visual Basic, text files
- I/O [Visual Basic], troubleshooting text files
- writing to files [Visual Basic], troubleshooting
- reading text files [Visual Basic], troubleshooting
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
ms.openlocfilehash: 8af4160d09f39f2622a007aef793173d614a8b44
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406630"
---
# <a name="troubleshooting-reading-from-and-writing-to-text-files-visual-basic"></a>Solución de problemas: Leer y escribir en archivos de texto (Visual Basic)

En este tema se tratan problemas habituales que surgen cuando se trabaja con archivos de texto y se sugiere un enfoque para cada uno.  
  
## <a name="common-problems"></a>Problemas habituales  

 Entre los problemas más frecuentes que se producen al trabajar con archivos de texto se incluyen excepciones de seguridad, codificaciones de archivos o rutas de acceso no válidas.  
  
### <a name="security-exceptions"></a>Excepciones de seguridad  

 Se genera <xref:System.Security.SecurityException> cuando se produce un error de seguridad. Suele ser consecuencia de que el usuario carezca de los permisos necesarios, lo que se puede resolver al agregar permisos o trabajar con archivos en almacenamiento aislado.  
  
### <a name="file-encodings"></a>Codificaciones de archivos  

 Las codificaciones de archivos, también denominadas codificaciones de caracteres, especifican cómo se representan los caracteres durante el procesamiento de texto. La presencia de caracteres inesperados en un archivo de texto puede deberse a una codificación incorrecta. Con la mayoría de los archivos, puede que una codificación sea preferible a otra en función de los caracteres del lenguaje que pueda controlar, aunque normalmente se prefiere Unicode. Para más información, vea [Codificación de archivos](file-encodings.md) y <xref:System.Text.Encoding>.  
  
### <a name="incorrect-paths"></a>Rutas de acceso incorrectas  

 Al analizar rutas de acceso de archivo, sobre todo rutas de acceso relativas, es fácil especificar datos equivocados. Muchos problemas pueden corregirse asegurándose de que especifica la ruta de acceso correcta. Para obtener más información, vea [How to: Parse File Paths in Visual Basic](how-to-parse-file-paths.md) (Cómo: Analizar rutas de acceso a archivos en Visual Basic).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- [Leer archivos](reading-from-files.md)
- [Escritura en archivos](writing-to-files.md)
- [Análisis de archivos de texto con el objeto TextFieldParser](parsing-text-files-with-the-textfieldparser-object.md)
