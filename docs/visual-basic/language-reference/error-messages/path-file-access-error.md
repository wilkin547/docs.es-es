---
title: "Error de acceso a la ruta o al archivo | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID75"
dev_langs: 
  - "VB"
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Error de acceso a la ruta o al archivo
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El sistema operativo no ha podido realizar una conexión entre la ruta de acceso y el nombre de archivo durante la operación de acceso al archivo o de acceso al disco.  
  
### Para corregir este error  
  
1.  Asegúrese de que la especificación de archivo tiene el formato correcto.  Un nombre de archivo puede contener una ruta de acceso completa \(absoluta\) o relativa.  Las rutas de acceso completas empiezan por el nombre de unidad \(si la ruta está en otra unidad\) y enumeran las rutas de acceso explícitas de la raíz a los archivos.  Las rutas de acceso que no sean completas son relativas a la unidad o el directorio actual.  
  
2.  Asegúrese de que no ha intentado guardar un archivo que reemplazaría a un archivo de sólo lectura existente.  Si este es el caso, cambie el atributo de sólo lectura del archivo de destino o guarde el archivo con otro nombre.  
  
3.  Asegúrese de que no ha intentado abrir un archivo de sólo lectura en modo`Output`o `Append` secuencial.  Si éste es el caso, abra el archivo en modo `Input` o cambie el atributo de sólo lectura del archivo.  
  
4.  Asegúrese de que no ha intentado cambiar un proyecto de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] dentro de una base de datos o documento.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)