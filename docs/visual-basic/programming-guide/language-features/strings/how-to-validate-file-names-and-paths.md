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
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="41659-102">Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41659-102">How to: Validate File Names and Paths in Visual Basic</span></span>

<span data-ttu-id="41659-103">Este ejemplo devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="41659-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="41659-104">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="41659-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41659-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="41659-105">Example</span></span>  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="41659-106">En este ejemplo no se comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="41659-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="41659-107">Tampoco comprueba si la aplicación tiene permiso para obtener acceso al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="41659-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41659-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="41659-108">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="41659-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41659-109">Validating Strings in Visual Basic</span></span>](validating-strings.md)
