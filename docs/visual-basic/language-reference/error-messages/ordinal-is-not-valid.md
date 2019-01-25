---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 351b7ee7f1cfc5199d878c33965770693227ccc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618969"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="2b89b-102">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="2b89b-102">Ordinal is not valid</span></span>
<span data-ttu-id="2b89b-103">La llamada a una biblioteca de vínculos dinámicos (DLL) indica que use un número en lugar de un nombre de procedimiento mediante el `#num` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="2b89b-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="2b89b-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="2b89b-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="2b89b-105">Un intento para convertir el `#num` expresión a un error de ordinal.</span><span class="sxs-lookup"><span data-stu-id="2b89b-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="2b89b-106">El `#num` especificado no se especifica ninguna función en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="2b89b-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="2b89b-107">Una biblioteca de tipos tiene una declaración no válida, lo que resulta en un uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="2b89b-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2b89b-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="2b89b-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="2b89b-109">Asegúrese de que la expresión representa un número válido, o llame al procedimiento por nombre.</span><span class="sxs-lookup"><span data-stu-id="2b89b-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="2b89b-110">Asegúrese de que `#num` identifica una función válida en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="2b89b-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="2b89b-111">Aislar la causa del problema marcando como comentario el código de la llamada del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2b89b-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="2b89b-112">Escribir un `Declare` declaración para el procedimiento y notificar el problema para el proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="2b89b-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b89b-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b89b-113">See also</span></span>
- [<span data-ttu-id="2b89b-114">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="2b89b-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
