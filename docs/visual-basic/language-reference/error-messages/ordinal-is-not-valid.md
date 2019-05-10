---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 740243c744a7ba5391659894812a00d80555fd80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665667"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="586ae-102">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="586ae-102">Ordinal is not valid</span></span>
<span data-ttu-id="586ae-103">La llamada a una biblioteca de vínculos dinámicos (DLL) indica que use un número en lugar de un nombre de procedimiento mediante el `#num` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="586ae-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="586ae-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="586ae-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="586ae-105">Un intento para convertir el `#num` expresión a un error de ordinal.</span><span class="sxs-lookup"><span data-stu-id="586ae-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="586ae-106">El `#num` especificado no se especifica ninguna función en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="586ae-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="586ae-107">Una biblioteca de tipos tiene una declaración no válida, lo que resulta en un uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="586ae-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="586ae-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="586ae-108">To correct this error</span></span>  
  
1. <span data-ttu-id="586ae-109">Asegúrese de que la expresión representa un número válido, o llame al procedimiento por nombre.</span><span class="sxs-lookup"><span data-stu-id="586ae-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="586ae-110">Asegúrese de que `#num` identifica una función válida en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="586ae-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="586ae-111">Aislar la causa del problema marcando como comentario el código de la llamada del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="586ae-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="586ae-112">Escribir un `Declare` declaración para el procedimiento y notificar el problema para el proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="586ae-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586ae-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="586ae-113">See also</span></span>

- [<span data-ttu-id="586ae-114">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="586ae-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
