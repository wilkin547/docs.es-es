---
title: Longitud de registro incorrecta
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 747d62cb41ef841b4486e0c7108c37a86929683e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="bad-record-length"></a><span data-ttu-id="5783b-102">Longitud de registro incorrecta</span><span class="sxs-lookup"><span data-stu-id="5783b-102">Bad record length</span></span>
<span data-ttu-id="5783b-103">Entre las causas posibles de este error se incluyen:</span><span class="sxs-lookup"><span data-stu-id="5783b-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="5783b-104">La longitud de una variable de registro especificada en una `FileGet`, `FileGetObject`, `FilePut` o `FilePutObject` instrucción difiere de la longitud especificada en la correspondiente `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5783b-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="5783b-105">La variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable.</span><span class="sxs-lookup"><span data-stu-id="5783b-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="5783b-106">La variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` tipo.</span><span class="sxs-lookup"><span data-stu-id="5783b-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5783b-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5783b-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="5783b-108">Asegúrese de que la suma de los tamaños de las variables de longitud fija en el tipo definido por el usuario define el tipo de la variable de registro es el mismo que el valor indicado en el `FileOpen` la instrucción `Len` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5783b-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2.  <span data-ttu-id="5783b-109">Si la variable en un `FilePut` o `FilePutObject` instrucción es o incluye una cadena de longitud variable, asegúrese de que la cadena de longitud variable tiene al menos 2 caracteres menor que la longitud de registro especificada en el `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5783b-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3.  <span data-ttu-id="5783b-110">Si la variable en un `FilePut` o `FilePutObject` es o incluye un `Variant` Asegúrese de que la cadena de longitud variable es al menos de 4 bytes más corto que la longitud de registro especificada en el `Len` cláusula de la `FileOpen` instrucción.</span><span class="sxs-lookup"><span data-stu-id="5783b-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5783b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="5783b-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
