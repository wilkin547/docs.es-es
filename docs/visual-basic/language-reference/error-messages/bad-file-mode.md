---
title: Modo de archivo incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 9a59faf1b6f845858e36efcabdf0758e41ad75dc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619747"
---
# <a name="bad-file-mode"></a>Modo de archivo incorrecto
Las instrucciones que se utilizan para manipular el contenido del archivo deben ser adecuadas para el modo en que se abrió el archivo. Entre las posibles causas se incluyen:  
  
- Un `FilePutObject` o `FileGetObject` instrucción especifica un archivo secuencial.  
  
- Un `Print` instrucción especifica un archivo abierto para un modo de acceso distinto `Output` o `Append`.  
  
- Un `Input` instrucción especifica un archivo abierto para un modo de acceso distinto `Input`  
  
- Se intenta escribir en un archivo de solo lectura.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de que `FilePutObject` y `FileGetObject` sólo hacen referencia a archivos abiertos para `Random` o `Binary` acceso.  
  
- Asegúrese de que `Print` especifica un archivo abierto para cualquiera `Output` o `Append` modo de acceso. Si no es así, utilice otra instrucción para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.  
  
- Asegúrese de que `Input` especifica un archivo abierto para `Input`. Si no es así, utilice otra instrucción para colocar datos en el archivo o vuelva a abrir el archivo en un modo adecuado.  
  
- Si está escribiendo en un archivo de solo lectura, cambie el estado de lectura/escritura del archivo o no intente escribir en él.  
  
- Use la funcionalidad disponible en el objeto `My.Computer.FileSystem` .  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.FileSystem>
- [Solución de problemas: Leer y escribir en archivos de texto](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
