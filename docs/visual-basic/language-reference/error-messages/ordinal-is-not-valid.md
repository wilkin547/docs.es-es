---
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871395"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="cad07-102">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="cad07-102">Ordinal is not valid</span></span>

<span data-ttu-id="cad07-103">La llamada a una biblioteca de vínculos dinámicos (DLL) indicada para usar un número en lugar de un nombre de procedimiento mediante la `#num` Sintaxis.</span><span class="sxs-lookup"><span data-stu-id="cad07-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="cad07-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="cad07-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="cad07-105">Error al intentar convertir la `#num` expresión a un ordinal.</span><span class="sxs-lookup"><span data-stu-id="cad07-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="cad07-106">El `#num` especificado no especifica ninguna función en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="cad07-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="cad07-107">Una biblioteca de tipos tiene una declaración no válida que produce el uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="cad07-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cad07-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="cad07-108">To correct this error</span></span>  
  
1. <span data-ttu-id="cad07-109">Asegúrese de que la expresión representa un número válido o llame al procedimiento por su nombre.</span><span class="sxs-lookup"><span data-stu-id="cad07-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="cad07-110">Asegúrese `#num` de que identifica una función válida en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="cad07-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="cad07-111">Aísle la llamada al procedimiento que causa el problema mediante el comentario del código.</span><span class="sxs-lookup"><span data-stu-id="cad07-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="cad07-112">Escriba una `Declare` instrucción para el procedimiento e informe del problema al proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="cad07-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad07-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cad07-113">See also</span></span>

- [<span data-ttu-id="cad07-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="cad07-114">Declare Statement</span></span>](../statements/declare-statement.md)
