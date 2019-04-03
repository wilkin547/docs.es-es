---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: b6da1031b60a4cd73c53588cf18992797c3fddab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839072"
---
# <a name="bad-file-name-or-number"></a>Número o nombre de archivo incorrecto
Se produjo un error al intentar obtener acceso al archivo especificado. Entre las posibles causas de este error son:  
  
-   La instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.  
  
-   Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.  
  
-   Una instrucción hace referencia a un nombre de archivo o un número que no es válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción. Tenga en cuenta que si se ha invocado el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.  
  
2.  Si el código genera números de archivo de forma algorítmica, asegúrese de que los números son válidos.  
  
3.  Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
