---
title: "El ordinal no es válido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="61edc-102">El ordinal no es válido</span><span class="sxs-lookup"><span data-stu-id="61edc-102">Ordinal is not valid</span></span>
<span data-ttu-id="61edc-103">La llamada a una biblioteca de vínculos dinámicos (DLL) indica el uso de un número en lugar de un nombre de procedimiento, mediante el `#num` sintaxis.</span><span class="sxs-lookup"><span data-stu-id="61edc-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="61edc-104">Este error tiene las siguientes causas posibles:</span><span class="sxs-lookup"><span data-stu-id="61edc-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="61edc-105">Un intento para convertir el `#num` expresión a un valor ordinal no se pudo.</span><span class="sxs-lookup"><span data-stu-id="61edc-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="61edc-106">El `#num` especificado no se especifica ninguna función en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="61edc-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="61edc-107">Una biblioteca de tipos tiene una declaración no válida que permite el uso interno de un número ordinal no válido.</span><span class="sxs-lookup"><span data-stu-id="61edc-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="61edc-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="61edc-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="61edc-109">Asegúrese de que la expresión representa un número válido o llame al procedimiento por nombre.</span><span class="sxs-lookup"><span data-stu-id="61edc-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="61edc-110">Asegúrese de que `#num` identifica una función válida en el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="61edc-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="61edc-111">Aislar la llamada de procedimiento que causa el problema marcando como comentario el código.</span><span class="sxs-lookup"><span data-stu-id="61edc-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="61edc-112">Escribir un `Declare` declaración para el procedimiento y notificar el problema al proveedor de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="61edc-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61edc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="61edc-113">See Also</span></span>  
 [<span data-ttu-id="61edc-114">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="61edc-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
