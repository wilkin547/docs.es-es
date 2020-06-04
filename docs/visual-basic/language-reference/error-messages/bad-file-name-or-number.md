---
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 11e866d9a8da7ad1ecc5f788fc31f6ac96d32f2c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409834"
---
# <a name="bad-file-name-or-number"></a>Número o nombre de archivo incorrecto
Error al intentar obtener acceso al archivo especificado. Entre las posibles causas de este error se encuentran:  
  
- Una instrucción hace referencia a un archivo con un nombre o número de archivo que no se especificó en la `FileOpen` instrucción o que se especificó en una `FileOpen` instrucción pero que se cerró posteriormente.  
  
- Una instrucción hace referencia a un archivo con un número que está fuera del intervalo de números de archivo.  
  
- Una instrucción hace referencia a un nombre de archivo o un número que no es válido.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que el nombre de archivo se especifica en una `FileOpen` instrucción. Tenga en cuenta que si se invoca la `FileClose` instrucción sin argumentos, es posible que haya cerrado accidentalmente todos los archivos abiertos.  
  
2. Si el código genera los números de archivo de forma algorítmica, asegúrese de que los números sean válidos.  
  
3. Compruebe los nombres de archivo para asegurarse de que se ajustan a las convenciones del sistema operativo.  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
