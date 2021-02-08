---
description: 'Más información acerca de: nombre o número de archivo incorrecto'
title: Número o nombre de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
ms.openlocfilehash: 6e568a721fb3606c5b4bc046041c9d6f24b6d126
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797073"
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
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
- [Convenciones de nomenclatura de Visual Basic](../../programming-guide/program-structure/naming-conventions.md)
