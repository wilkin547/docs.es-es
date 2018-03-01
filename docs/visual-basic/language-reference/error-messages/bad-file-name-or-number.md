---
title: "Número o nombre de archivo incorrecto"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a>Número o nombre de archivo incorrecto
Se produjo un error al intentar obtener acceso al archivo especificado. Entre las posibles causas de este error son:  
  
-   Una instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.  
  
-   Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.  
  
-   Una instrucción hace referencia a un nombre de archivo o un número que no es válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción. Tenga en cuenta que si invoca el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.  
  
2.  Si el código está generando números de los archivos de forma algorítmica, asegúrese de que los números son válidos.  
  
3.  Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
