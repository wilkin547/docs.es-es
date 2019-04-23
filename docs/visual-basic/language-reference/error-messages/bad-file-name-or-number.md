---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 2e5d4a3ddd66df85dc4758e22b36ac1ed495659a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322165"
---
# <a name="bad-file-name-or-number"></a>Número o nombre de archivo incorrecto
Se produjo un error al intentar obtener acceso al archivo especificado. Entre las posibles causas de este error son:  
  
-   La instrucción hace referencia a un archivo con un nombre de archivo o un número que no se especificó en el `FileOpen` instrucción o que se especificó en un `FileOpen` instrucción pero era posteriormente cerrado.  
  
-   Una instrucción hace referencia a un archivo con un número que está fuera del intervalo del número de archivos.  
  
-   Una instrucción hace referencia a un nombre de archivo o un número que no es válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que se especifica el nombre de archivo en un `FileOpen` instrucción. Tenga en cuenta que si se ha invocado el `FileClose` instrucción sin argumentos, puede haber accidentalmente cerrado todos los archivos abiertos.  
  
2. Si el código genera números de archivo de forma algorítmica, asegúrese de que los números son válidos.  
  
3. Compruebe los nombres de archivo para asegurarse de que se ajusten a las convenciones del sistema operativo.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenciones de nomenclatura de Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
