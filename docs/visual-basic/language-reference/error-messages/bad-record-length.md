---
description: 'Más información acerca de: longitud de registro incorrecta'
title: Longitud de registro incorrecta
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 820597a3c4e157894aadb280ae141098cae7eed4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797060"
---
# <a name="bad-record-length"></a>Longitud de registro incorrecta

Entre las causas posibles de este error se incluyen:  
  
- La longitud de una variable de registro especificada en `FileGet` una `FileGetObject` `FilePut` instrucción, o `FilePutObject` difiere de la longitud especificada en la `FileOpen` instrucción correspondiente.  
  
- La variable de una `FilePut` `FilePutObject` instrucción o es o incluye una cadena de longitud variable.  
  
- La variable en `FilePut` o `FilePutObject` es o incluye un `Variant` tipo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Asegúrese de que la suma de los tamaños de las variables de longitud fija en el tipo definido por el usuario que define el tipo de la variable de registro es igual que el valor indicado en la `FileOpen` cláusula de la instrucción `Len` .  
  
2. Si la variable de una `FilePut` `FilePutObject` instrucción o es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres más cortos que la longitud de registro especificada en la `Len` cláusula de la `FileOpen` instrucción.  
  
3. Si la variable en `FilePut` o `FilePutObject` es o incluye un, `Variant` Asegúrese de que la cadena de longitud variable tiene al menos 4 bytes más cortos que la longitud de registro especificada en la `Len` cláusula de la `FileOpen` instrucción.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
