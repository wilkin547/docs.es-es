---
title: Procedimiento para validar rutas de acceso y nombres de archivo
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 3b4695dfbcaf05c73bd53af5be7a49d081eb8e47
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410585"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic
Este ejemplo devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o una ruta de acceso. La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 En este ejemplo no se comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema. Tampoco comprueba si la aplicación tiene permiso para obtener acceso al recurso del sistema de archivos con el nombre especificado.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Validar cadenas en Visual Basic](validating-strings.md)
