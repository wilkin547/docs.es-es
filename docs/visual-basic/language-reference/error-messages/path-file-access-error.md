---
title: Error de acceso al archivo de la ruta de acceso
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c86d46c884617be152a5954426e9ddd6ef61651
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="pathfile-access-error"></a>Error de acceso a la ruta o al archivo
Durante una operación de acceso a archivos o acceso al disco, el sistema operativo no pudo realizar una conexión entre la ruta de acceso y el nombre de archivo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que la especificación de archivo tiene el formato correcto. Un nombre de archivo puede contener un acceso completa (absoluta) o relativa ruta de acceso. Ruta de acceso completa se inicia con el nombre de unidad (si la ruta de acceso está en otra unidad) y muestra la ruta de acceso explícita desde la raíz en el archivo. Cualquier ruta de acceso que no es un nombre completo es relativa a la unidad actual y el directorio.  
  
2.  Asegúrese de que no ha intentado guardar un archivo que reemplaza un archivo de sólo lectura existente. Si este es el caso, cambie el atributo de sólo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.  
  
3.  Asegúrese de que no ha intentado abrir un archivo de solo lectura en secuencial `Output` o `Append` modo. Si este es el caso, abra el archivo en `Input` modo o cambiar el atributo de sólo lectura del archivo.  
  
4.  Asegúrese de que no intentó cambiar un [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] proyecto dentro de una base de datos o el documento.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
