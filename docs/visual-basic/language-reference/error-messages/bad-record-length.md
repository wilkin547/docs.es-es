---
title: Longitud de registro incorrecta
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935257"
---
# <a name="bad-record-length"></a><span data-ttu-id="c0dbd-102">Longitud de registro incorrecta</span><span class="sxs-lookup"><span data-stu-id="c0dbd-102">Bad record length</span></span>
<span data-ttu-id="c0dbd-103">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="c0dbd-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="c0dbd-104">La longitud de una variable de registro especificada en un `FileGet`, `FileGetObject`, `FilePut` o `FilePutObject` instrucción difiere de la longitud especificada en la correspondiente `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="c0dbd-105">La variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="c0dbd-106">La variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` tipo.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c0dbd-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c0dbd-107">To correct this error</span></span>  
  
1. <span data-ttu-id="c0dbd-108">Asegúrese de que la suma de los tamaños de las variables de longitud fija en el tipo definido por el usuario define el tipo de la variable de registro es el mismo que el valor se indica en la `FileOpen` la instrucción `Len` cláusula.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="c0dbd-109">Si la variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres menor que la longitud de registro especificada en el `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="c0dbd-110">Si la variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` Asegúrese de que la cadena de longitud variable es menor que la longitud del registro especificada en al menos 4 bytes el `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c0dbd-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0dbd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0dbd-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
