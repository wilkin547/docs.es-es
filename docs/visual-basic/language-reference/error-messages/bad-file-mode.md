---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: bccbbbeb79f38790a4664b0152ca3378fb55448d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="bad-file-mode"></a>Modo de archivo incorrecto
Las instrucciones que se utilizan para manipular el contenido del archivo deben ser adecuadas para el modo en que se abrió el archivo. Entre las posibles causas se incluyen:  
  
-   A `FilePutObject` o `FileGetObject` instrucción especifica un archivo secuencial.  
  
-   A `Print` instrucción especifica un archivo abierto para un modo de acceso distintos de `Output` o `Append`.  
  
-   Un `Input` instrucción especifica un archivo abierto para un modo de acceso distinto `Input`  
  
-   Ha intentado escribir en un archivo de solo lectura.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que `FilePutObject` y `FileGetObject` sólo hacen referencia a archivos abiertos para `Random` o `Binary` acceso.  
  
-   Asegúrese de que `Print` especifica un archivo abierto para cualquiera `Output` o `Append` modo de acceso. De lo contrario, utilice una instrucción diferentes para colocar datos en el archivo o volver a abrir el archivo en un modo adecuado.  
  
-   Asegúrese de que `Input` especifica un archivo abierto para `Input`. Si no es así, utilice otra instrucción para colocar datos en el archivo o volver a abrir el archivo en un modo adecuado.  
  
-   Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura/escritura del archivo o no intente escribir en él.  
  
-   Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [Solución de problemas: Leer y escribir en archivos de texto](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
