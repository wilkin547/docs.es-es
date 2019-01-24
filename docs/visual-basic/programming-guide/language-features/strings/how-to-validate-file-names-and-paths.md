---
title: Procedimiento Validar los nombres de archivo y rutas de acceso en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c0d39ecbaf9ca23c72e45b8839d268fbc38fe48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648461"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="79fcf-102">Procedimiento Validar los nombres de archivo y rutas de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79fcf-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="79fcf-103">Este ejemplo se devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="79fcf-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="79fcf-104">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="79fcf-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79fcf-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79fcf-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="79fcf-106">En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="79fcf-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="79fcf-107">No comprueba si la aplicación tiene permiso para acceder al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="79fcf-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79fcf-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="79fcf-108">See also</span></span>
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="79fcf-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79fcf-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
