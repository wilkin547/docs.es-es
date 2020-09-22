---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 99b84902ddf032f2ecb6e26400e200bea862dfdf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875151"
---
# <a name="bad-file-mode"></a>Modo de archivo incorrecto

Las instrucciones usadas para manipular el contenido del archivo deben ser adecuadas para el modo en el que se abrió el archivo. Entre las causas posibles se incluyen las siguientes:  
  
- Una `FilePutObject` `FileGetObject` instrucción o especifica un archivo secuencial.  
  
- Una `Print` instrucción especifica un archivo abierto para un modo de acceso distinto de `Output` o `Append` .  
  
- Una `Input` instrucción especifica un archivo abierto para un modo de acceso distinto de `Input`  
  
- Intento de escribir en un archivo de solo lectura.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de `FilePutObject` que `FileGetObject` solo se hace referencia a los archivos abiertos para `Random` o `Binary` acceso.  
  
- Asegúrese `Print` de que especifica un archivo abierto para `Output` el `Append` modo de acceso o. Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.  
  
- Asegúrese `Input` de que especifica un archivo abierto para `Input` . Si no es así, use una instrucción diferente para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.  
  
- Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura y escritura del archivo o no intente escribir en él.  
  
- Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.FileSystem>
- [Solución del problema: leer y escribir en archivos de texto](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
