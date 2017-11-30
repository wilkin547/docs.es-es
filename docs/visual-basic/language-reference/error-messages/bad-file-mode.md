---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a>Modo de archivo incorrecto
Las instrucciones que se utilizan para manipular el contenido del archivo deben ser adecuadas para el modo en que se abrió el archivo. Entre las posibles causas se incluyen:  
  
-   A `FilePutObject` o `FileGetObject` instrucción especifica un archivo secuencial.  
  
-   A `Print` instrucción especifica un archivo abierto para un modo de acceso distintos de `Output` o `Append`.  
  
-   Un `Input` instrucción especifica un archivo abierto para un modo de acceso distinto`Input`  
  
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
