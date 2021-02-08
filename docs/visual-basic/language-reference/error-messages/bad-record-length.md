---
description: 'Más información acerca de: longitud de registro incorrecta'
title: Longitud de registro incorrecta
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 820597a3c4e157894aadb280ae141098cae7eed4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797060"
---
# <a name="bad-record-length"></a><span data-ttu-id="ac1f4-103">Longitud de registro incorrecta</span><span class="sxs-lookup"><span data-stu-id="ac1f4-103">Bad record length</span></span>

<span data-ttu-id="ac1f4-104">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="ac1f4-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="ac1f4-105">La longitud de una variable de registro especificada en `FileGet` una `FileGetObject` `FilePut` instrucción, o `FilePutObject` difiere de la longitud especificada en la `FileOpen` instrucción correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ac1f4-105">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="ac1f4-106">La variable de una `FilePut` `FilePutObject` instrucción o es o incluye una cadena de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="ac1f4-106">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="ac1f4-107">La variable en `FilePut` o `FilePutObject` es o incluye un `Variant` tipo.</span><span class="sxs-lookup"><span data-stu-id="ac1f4-107">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac1f4-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="ac1f4-108">To correct this error</span></span>  
  
1. <span data-ttu-id="ac1f4-109">Asegúrese de que la suma de los tamaños de las variables de longitud fija en el tipo definido por el usuario que define el tipo de la variable de registro es igual que el valor indicado en la `FileOpen` cláusula de la instrucción `Len` .</span><span class="sxs-lookup"><span data-stu-id="ac1f4-109">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="ac1f4-110">Si la variable de una `FilePut` `FilePutObject` instrucción o es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres más cortos que la longitud de registro especificada en la `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ac1f4-110">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="ac1f4-111">Si la variable en `FilePut` o `FilePutObject` es o incluye un, `Variant` Asegúrese de que la cadena de longitud variable tiene al menos 4 bytes más cortos que la longitud de registro especificada en la `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="ac1f4-111">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac1f4-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac1f4-112">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
