---
description: 'Más información acerca de: la codificación no se puede establecer en nada'
title: La codificación no se puede establecer en Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 4fa9cbd9488501b5295da8d8ace41ef06a706c12
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463000"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>La codificación no se puede establecer en Nothing

Error en un intento de leer un archivo o escribir en él porque el parámetro `encoding` se ha establecido en `Nothing` pero requiere un valor válido.  
  
 <xref:System.Text.Encoding> se usa para determinar qué codificación se debe usar al escribir en un archivo. El valor predeterminado es UTF-8.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Proporcione un valor válido para el parámetro `encoding` .  
  
## <a name="see-also"></a>Consulte también

- [Codificaciones de archivos](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [Lectura de archivos](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Escritura en archivos](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. Computer. FileSystem. ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. Computer. FileSystem. WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
