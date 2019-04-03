---
title: Sobrecarga de procedimiento (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 6e8d1fa72c60c4fa3d2237ad24c2d1b4891a7bf2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828243"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="bfda9-102">Sobrecarga de procedimiento (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfda9-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="bfda9-103">*Sobrecarga* un procedimiento significa definirlo en varias versiones, con el mismo nombre pero con distintas listas de parámetros.</span><span class="sxs-lookup"><span data-stu-id="bfda9-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="bfda9-104">El propósito de sobrecarga es definir varias versiones estrechamente relacionadas de un procedimiento sin tener que distinguirlas por su nombre.</span><span class="sxs-lookup"><span data-stu-id="bfda9-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="bfda9-105">Hacer esto mediante la variación de la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="bfda9-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="bfda9-106">Reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="bfda9-106">Overloading Rules</span></span>  
 <span data-ttu-id="bfda9-107">Cuando se sobrecarga un procedimiento, se aplican las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bfda9-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="bfda9-108">**Mismo nombre**.</span><span class="sxs-lookup"><span data-stu-id="bfda9-108">**Same Name**.</span></span> <span data-ttu-id="bfda9-109">Cada versión sobrecargada debe usar el mismo nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bfda9-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="bfda9-110">**Firma diferente**.</span><span class="sxs-lookup"><span data-stu-id="bfda9-110">**Different Signature**.</span></span> <span data-ttu-id="bfda9-111">Cada versión sobrecargada debe diferir de todas las versiones sobrecargadas en al menos uno de los siguientes aspectos:</span><span class="sxs-lookup"><span data-stu-id="bfda9-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="bfda9-112">Número de parámetros</span><span class="sxs-lookup"><span data-stu-id="bfda9-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="bfda9-113">Orden de los parámetros</span><span class="sxs-lookup"><span data-stu-id="bfda9-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="bfda9-114">Tipos de datos de los parámetros</span><span class="sxs-lookup"><span data-stu-id="bfda9-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="bfda9-115">Número de parámetros de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="bfda9-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="bfda9-116">Tipo de valor devuelto (solo para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="bfda9-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="bfda9-117">Junto con el nombre del procedimiento, los elementos anteriores se denominan colectivamente la *firma* del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bfda9-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="bfda9-118">Cuando se llama a un procedimiento sobrecargado, el compilador utiliza la firma para comprobar que la llamada coincide con la definición.</span><span class="sxs-lookup"><span data-stu-id="bfda9-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="bfda9-119">**Los elementos no forma parte de la firma**.</span><span class="sxs-lookup"><span data-stu-id="bfda9-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="bfda9-120">No se pueden sobrecargar un procedimiento sin modificar la firma.</span><span class="sxs-lookup"><span data-stu-id="bfda9-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="bfda9-121">En concreto, no se puede sobrecargar un procedimiento cambiando únicamente uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="bfda9-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="bfda9-122">Palabras clave de modificador de procedimiento, como `Public`, `Shared`, y `Static`</span><span class="sxs-lookup"><span data-stu-id="bfda9-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="bfda9-123">Nombres de parámetro de tipo o parámetro</span><span class="sxs-lookup"><span data-stu-id="bfda9-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="bfda9-124">Restricciones de parámetro de tipo (para un procedimiento genérico)</span><span class="sxs-lookup"><span data-stu-id="bfda9-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="bfda9-125">Palabras clave de modificador de parámetro, como `ByRef` y `Optional`</span><span class="sxs-lookup"><span data-stu-id="bfda9-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="bfda9-126">Si devuelve un valor</span><span class="sxs-lookup"><span data-stu-id="bfda9-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="bfda9-127">El tipo de datos del valor devuelto (excepto para un operador de conversión)</span><span class="sxs-lookup"><span data-stu-id="bfda9-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="bfda9-128">Los elementos de la lista anterior no forman parte de la firma.</span><span class="sxs-lookup"><span data-stu-id="bfda9-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="bfda9-129">Aunque no se pueden utilizar para diferenciar entre versiones sobrecargadas, se puede variar entre las versiones sobrecargadas que correctamente se diferencian por sus firmas.</span><span class="sxs-lookup"><span data-stu-id="bfda9-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="bfda9-130">**Los argumentos enlazados**.</span><span class="sxs-lookup"><span data-stu-id="bfda9-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="bfda9-131">Si piensa pasar una variable de objeto enlazado en tiempo de ejecución a una versión sobrecargada, debe declarar el parámetro apropiado como <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="bfda9-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="bfda9-132">Varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="bfda9-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="bfda9-133">Supongamos que está escribiendo un `Sub` procedimiento para registrar una transacción en el saldo de un cliente y desea poder hacer referencia al cliente por nombre o por número de cuenta.</span><span class="sxs-lookup"><span data-stu-id="bfda9-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="bfda9-134">Para dar cabida a esto, puede definir dos diferentes `Sub` procedimientos, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bfda9-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="bfda9-135">Versiones sobrecargadas</span><span class="sxs-lookup"><span data-stu-id="bfda9-135">Overloaded Versions</span></span>  
 <span data-ttu-id="bfda9-136">Es una alternativa a la sobrecarga de un único nombre de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bfda9-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="bfda9-137">Puede usar el [sobrecargas](../../../../visual-basic/language-reference/modifiers/overloads.md) palabra clave para definir una versión del procedimiento para cada lista de parámetros, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="bfda9-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="bfda9-138">Sobrecargas adicionales</span><span class="sxs-lookup"><span data-stu-id="bfda9-138">Additional Overloads</span></span>  
 <span data-ttu-id="bfda9-139">Si desea aceptar un importe de transacción en el `Decimal` o `Single`, se podrían sobrecargar aún más `post` para permitir esta variación.</span><span class="sxs-lookup"><span data-stu-id="bfda9-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="bfda9-140">Si lo hizo en cada una de las sobrecargas en el ejemplo anterior, tendría cuatro `Sub` procedimientos, todo ello con el mismo nombre pero con cuatro firmas diferentes.</span><span class="sxs-lookup"><span data-stu-id="bfda9-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="bfda9-141">Ventajas de la sobrecarga</span><span class="sxs-lookup"><span data-stu-id="bfda9-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="bfda9-142">La ventaja de sobrecargar un procedimiento es en la flexibilidad de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bfda9-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="bfda9-143">Para usar el `post` procedimiento declarado en el ejemplo anterior, el código de llamada puede obtener la identificación del cliente como un `String` o un `Integer`y, a continuación, llamar al mismo procedimiento en ambos casos.</span><span class="sxs-lookup"><span data-stu-id="bfda9-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="bfda9-144">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bfda9-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a><span data-ttu-id="bfda9-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfda9-145">See also</span></span>

- [<span data-ttu-id="bfda9-146">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="bfda9-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="bfda9-147">Cómo: Definir varias versiones de un procedimiento</span><span class="sxs-lookup"><span data-stu-id="bfda9-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="bfda9-148">Cómo: Llamar a un procedimiento sobrecargado</span><span class="sxs-lookup"><span data-stu-id="bfda9-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="bfda9-149">Cómo: Sobrecargar un procedimiento que toma parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="bfda9-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="bfda9-150">Cómo: Sobrecargar un procedimiento que toma un número indefinido de parámetros</span><span class="sxs-lookup"><span data-stu-id="bfda9-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="bfda9-151">Consideraciones sobre la sobrecarga de procedimientos</span><span class="sxs-lookup"><span data-stu-id="bfda9-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="bfda9-152">Resolución de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="bfda9-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="bfda9-153">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="bfda9-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="bfda9-154">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfda9-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
