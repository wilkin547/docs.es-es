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
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="83e30-102">Procedimiento Validar los nombres de archivo y rutas de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83e30-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="83e30-103">Este ejemplo se devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="83e30-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="83e30-104">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="83e30-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e30-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83e30-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="83e30-106">En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="83e30-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="83e30-107">No comprueba si la aplicación tiene permiso para acceder al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="83e30-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e30-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="83e30-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="83e30-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83e30-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
