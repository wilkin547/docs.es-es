---
title: La codificación no se puede establecer en Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970331"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>La codificación no se puede establecer en Nothing
Error en un intento de leer un archivo o escribir en él porque el parámetro `encoding` se ha establecido en `Nothing` pero requiere un valor válido.  
  
 <xref:System.Text.Encoding> se usa para determinar qué codificación se debe usar al escribir en un archivo. El valor predeterminado es UTF-8.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Proporcione un valor válido para el parámetro `encoding` .  
  
## <a name="see-also"></a>Vea también

- [Codificaciones de archivos](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [Leer archivos](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Escritura en archivos](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
