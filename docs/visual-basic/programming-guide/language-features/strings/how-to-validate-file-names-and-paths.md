---
title: Procedimiento Validar los nombres de archivo y rutas de acceso en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032180"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Procedimiento Validar los nombres de archivo y rutas de acceso en Visual Basic
Este ejemplo se devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso. La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema. No comprueba si la aplicación tiene permiso para acceder al recurso del sistema de archivos con el nombre especificado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
