---
title: Error de acceso al archivo de la ruta de acceso
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 83ce8615b173a6f5835347ebc561a793655ec8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="pathfile-access-error"></a>Error de acceso a la ruta o al archivo
Durante una operación de acceso a archivos o acceso al disco, el sistema operativo no pudo realizar una conexión entre la ruta de acceso y el nombre de archivo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que la especificación de archivo tiene el formato correcto. Un nombre de archivo puede contener un acceso completa (absoluta) o relativa ruta de acceso. Ruta de acceso completa se inicia con el nombre de unidad (si la ruta de acceso está en otra unidad) y muestra la ruta de acceso explícita desde la raíz en el archivo. Cualquier ruta de acceso que no es un nombre completo es relativa a la unidad actual y el directorio.  
  
2.  Asegúrese de que no ha intentado guardar un archivo que reemplaza un archivo de sólo lectura existente. Si este es el caso, cambie el atributo de sólo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.  
  
3.  Asegúrese de que no ha intentado abrir un archivo de solo lectura en secuencial `Output` o `Append` modo. Si este es el caso, abra el archivo en `Input` modo o cambiar el atributo de sólo lectura del archivo.  
  
4.  Asegúrese de que no intentó cambiar un proyecto de Visual Basic dentro de una base de datos o el documento.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
