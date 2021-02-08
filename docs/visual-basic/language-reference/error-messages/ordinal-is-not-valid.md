---
description: 'Más información acerca de: el ordinal no es válido'
title: El ordinal no es válido
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 7c58675a08d3821cd05ba0109e5ce0107c68e497
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795526"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="62097-103">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="62097-103">Ordinal is not valid</span></span>

<span data-ttu-id="62097-104">La llamada a una biblioteca de vínculos dinámicos (DLL) indicada para usar un número en lugar de un nombre de procedimiento mediante la `#num` Sintaxis.</span><span class="sxs-lookup"><span data-stu-id="62097-104">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="62097-105">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="62097-105">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="62097-106">Error al intentar convertir la `#num` expresión a un ordinal.</span><span class="sxs-lookup"><span data-stu-id="62097-106">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="62097-107">El `#num` especificado no especifica ninguna función en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="62097-107">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="62097-108">Una biblioteca de tipos tiene una declaración no válida que produce el uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="62097-108">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="62097-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="62097-109">To correct this error</span></span>  
  
1. <span data-ttu-id="62097-110">Asegúrese de que la expresión representa un número válido o llame al procedimiento por su nombre.</span><span class="sxs-lookup"><span data-stu-id="62097-110">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="62097-111">Asegúrese `#num` de que identifica una función válida en el archivo dll.</span><span class="sxs-lookup"><span data-stu-id="62097-111">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="62097-112">Aísle la llamada al procedimiento que causa el problema mediante el comentario del código.</span><span class="sxs-lookup"><span data-stu-id="62097-112">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="62097-113">Escriba una `Declare` instrucción para el procedimiento e informe del problema al proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="62097-113">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62097-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="62097-114">See also</span></span>

- [<span data-ttu-id="62097-115">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="62097-115">Declare Statement</span></span>](../statements/declare-statement.md)
