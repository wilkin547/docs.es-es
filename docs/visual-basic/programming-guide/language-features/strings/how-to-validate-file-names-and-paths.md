---
title: 'Cómo: validar nombres de archivo y rutas de acceso'
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: cc4d275d469860aa19c45ca0fe0401b709b42d82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344362"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="6af49-102">Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6af49-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="6af49-103">Este ejemplo devuelve un valor `Boolean` que indica si una cadena representa un nombre de archivo o una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="6af49-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="6af49-104">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="6af49-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6af49-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6af49-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="6af49-106">En este ejemplo no se comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6af49-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="6af49-107">Tampoco comprueba si la aplicación tiene permiso para obtener acceso al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="6af49-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af49-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="6af49-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="6af49-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6af49-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
