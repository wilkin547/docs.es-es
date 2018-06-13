---
title: 'Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647809"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic
Este ejemplo devuelve una `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso. La validación comprueba si el nombre contiene caracteres que no se admiten en el sistema de archivos.  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema. No comprueba si la aplicación tiene permiso para tener acceso al recurso de sistema de archivos con el nombre especificado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [Validar cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
