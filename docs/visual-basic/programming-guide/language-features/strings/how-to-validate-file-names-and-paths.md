---
description: 'Más información acerca de cómo: validar nombres de archivo y rutas de acceso en Visual Basic'
title: Procedimiento para validar rutas de acceso y nombres de archivo
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: 02a48ea7cbf3291cb2fe1c64c4e636a273842546
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429745"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="62c57-103">Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62c57-103">How to: Validate File Names and Paths in Visual Basic</span></span>

<span data-ttu-id="62c57-104">Este ejemplo devuelve un `Boolean` valor que indica si una cadena representa un nombre de archivo o una ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="62c57-104">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="62c57-105">La validación comprueba si el nombre contiene caracteres no permitidos por el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="62c57-105">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62c57-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62c57-106">Example</span></span>  

 [!code-vb[VbVbcnRegEx#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#4)]  
  
 <span data-ttu-id="62c57-107">En este ejemplo no se comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="62c57-107">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="62c57-108">Tampoco comprueba si la aplicación tiene permiso para obtener acceso al recurso del sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="62c57-108">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c57-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62c57-109">See also</span></span>

- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [<span data-ttu-id="62c57-110">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62c57-110">Validating Strings in Visual Basic</span></span>](validating-strings.md)
