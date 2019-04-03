---
title: Filtrar Validar los nombres de archivo y rutas de acceso en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c8e01a0f5a3f99fdbc424d6cd7d224367c7bad08
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835809"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="dbb3c-102">Filtrar Validar los nombres de archivo y rutas de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbb3c-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="dbb3c-103">Este ejemplo se devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="dbb3c-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="dbb3c-104">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="dbb3c-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbb3c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dbb3c-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="dbb3c-106">En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="dbb3c-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="dbb3c-107">No comprueba si la aplicación tiene permiso para acceder al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="dbb3c-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb3c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbb3c-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="dbb3c-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dbb3c-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
