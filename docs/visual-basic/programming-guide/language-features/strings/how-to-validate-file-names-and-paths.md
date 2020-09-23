---
title: Procedimiento para validar rutas de acceso y nombres de archivo
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: b722222ea8b8088a6b326eef27147c08f8419272
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072657"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic

Este ejemplo devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o una ruta de acceso. La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.  
  
## <a name="example"></a>Ejemplo  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 En este ejemplo no se comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema. Tampoco comprueba si la aplicación tiene permiso para obtener acceso al recurso del sistema de archivos con el nombre especificado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Validar cadenas en Visual Basic](validating-strings.md)
