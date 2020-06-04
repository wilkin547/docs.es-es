---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7b9bd8435b56dd5e33d14eb35d76aacc7d60c8b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413058"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="7c03b-102">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="7c03b-102">Ordinal is not valid</span></span>
<span data-ttu-id="7c03b-103">La llamada a una biblioteca de vínculos dinámicos (DLL) indicada para usar un número en lugar de un nombre de procedimiento mediante la `#num` Sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7c03b-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="7c03b-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="7c03b-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="7c03b-105">Error al intentar convertir la `#num` expresión a un ordinal.</span><span class="sxs-lookup"><span data-stu-id="7c03b-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="7c03b-106">El `#num` especificado no especifica ninguna función en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="7c03b-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="7c03b-107">Una biblioteca de tipos tiene una declaración no válida que produce el uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="7c03b-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7c03b-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="7c03b-108">To correct this error</span></span>  
  
1. <span data-ttu-id="7c03b-109">Asegúrese de que la expresión representa un número válido o llame al procedimiento por su nombre.</span><span class="sxs-lookup"><span data-stu-id="7c03b-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="7c03b-110">Asegúrese `#num` de que identifica una función válida en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="7c03b-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="7c03b-111">Aísle la llamada al procedimiento que causa el problema mediante el comentario del código.</span><span class="sxs-lookup"><span data-stu-id="7c03b-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="7c03b-112">Escriba una `Declare` instrucción para el procedimiento e informe del problema al proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="7c03b-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c03b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7c03b-113">See also</span></span>

- [<span data-ttu-id="7c03b-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="7c03b-114">Declare Statement</span></span>](../statements/declare-statement.md)
