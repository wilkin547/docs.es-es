---
title: "Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c50d09dd7160992ffd95ececeff623a8aa93d2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a><span data-ttu-id="f782a-102">Cómo: Validar rutas de acceso y nombres de archivo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f782a-102">How to: Validate File Names and Paths in Visual Basic</span></span>
<span data-ttu-id="f782a-103">Este ejemplo devuelve una `Boolean` valor que indica si una cadena representa un nombre de archivo o ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f782a-103">This example returns a `Boolean` value that indicates whether a string represents a file name or path.</span></span> <span data-ttu-id="f782a-104">La validación comprueba si el nombre contiene caracteres que no se admiten en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="f782a-104">The validation checks if the name contains characters that are not allowed by the file system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f782a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f782a-105">Example</span></span>  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 <span data-ttu-id="f782a-106">En este ejemplo no comprueba si el nombre ha colocado incorrectamente dos puntos o directorios sin nombre, o si la longitud del nombre supera la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="f782a-106">This example does not check if the name has incorrectly placed colons, or directories with no name, or if the length of the name exceeds the system-defined maximum length.</span></span> <span data-ttu-id="f782a-107">No comprueba si la aplicación tiene permiso para tener acceso al recurso de sistema de archivos con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="f782a-107">It also does not check if the application has permission to access the file-system resource with the specified name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f782a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f782a-108">See Also</span></span>  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [<span data-ttu-id="f782a-109">Validar cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f782a-109">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
