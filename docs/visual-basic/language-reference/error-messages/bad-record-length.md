---
title: Longitud de registro incorrecta
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 37d9da67656ec4821903d8ba67a27ef10f1a437d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728875"
---
# <a name="bad-record-length"></a>Longitud de registro incorrecta
Entre las causas posibles de este error se incluyen:  
  
-   La longitud de una variable de registro especificada en un `FileGet`, `FileGetObject`, `FilePut` o `FilePutObject` instrucción difiere de la longitud especificada en la correspondiente `FileOpen` instrucción.  
  
-   La variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable.  
  
-   La variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` tipo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que la suma de los tamaños de las variables de longitud fija en el tipo definido por el usuario define el tipo de la variable de registro es el mismo que el valor se indica en la `FileOpen` la instrucción `Len` cláusula.  
  
2.  Si la variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres menor que la longitud de registro especificada en el `Len` cláusula de la `FileOpen` instrucción.  
  
3.  Si la variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` Asegúrese de que la cadena de longitud variable es menor que la longitud del registro especificada en al menos 4 bytes el `Len` cláusula de la `FileOpen` instrucción.  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
