---
title: Error de acceso de archivo de la ruta de acceso | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ac730bac76540331206daebe600445ca54cc15a9
ms.lasthandoff: 03/13/2017

---
# <a name="pathfile-access-error"></a>Error de acceso a la ruta o al archivo
Durante una operación de acceso a archivos o acceso al disco, el sistema operativo no pudo realizar una conexión entre la ruta de acceso y el nombre de archivo.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Asegúrese de que la especificación de archivo tiene el formato correcto. Un nombre de archivo puede contener un nombre completo (absoluta) o relativa ruta de acceso. Una ruta de acceso completa comienza con el nombre de unidad (si la ruta está en otra unidad) y muestra la ruta de acceso explícita desde la raíz del archivo. Cualquier ruta de acceso no es un nombre completo es relativa a la unidad y directorio actuales.  
  
2.  Asegúrese de que no ha intentado guardar un archivo que reemplazaría a un archivo de sólo lectura existente. Si es así, cambie el atributo de sólo lectura del archivo de destino o guarde el archivo con un nombre de archivo diferente.  
  
3.  Asegúrese de que no ha intentado abrir un archivo de sólo lectura en secuencial`Output`o `Append` modo. Si este es el caso, abra el archivo en `Input` modo o cambiar el atributo de sólo lectura del archivo.  
  
4.  Asegúrese de que no ha intentado cambiar un [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proyecto dentro de una base de datos o documento.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)
