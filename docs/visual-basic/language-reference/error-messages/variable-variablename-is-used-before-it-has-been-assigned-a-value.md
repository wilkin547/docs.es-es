---
title: La variable '<variablename>' se utiliza antes de ser asignada a un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 46551a917aeb794c8d35985076b67a315386f628
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766732"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="77bfd-102">Variable '\<NombreDeVariable >' se utiliza antes de que se le ha asignado un valor</span><span class="sxs-lookup"><span data-stu-id="77bfd-102">Variable '\<variablename>' is used before it has been assigned a value</span></span>
<span data-ttu-id="77bfd-103">Variable '\<NombreDeVariable >' se utiliza antes de que se le ha asignado un valor.</span><span class="sxs-lookup"><span data-stu-id="77bfd-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="77bfd-104">Podría producirse una excepción de referencia nula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77bfd-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="77bfd-105">Una aplicación tiene al menos una ruta de acceso posibles a través de su código que lee una variable antes de asignar cualquier valor a él.</span><span class="sxs-lookup"><span data-stu-id="77bfd-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="77bfd-106">Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="77bfd-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="77bfd-107">Para un tipo de datos de referencia, el valor predeterminado es [Nothing](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="77bfd-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="77bfd-108">Leer una variable de referencia que tiene un valor de `Nothing` puede producir una excepción <xref:System.NullReferenceException> en algunas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="77bfd-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="77bfd-109">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="77bfd-109">By default, this message is a warning.</span></span> <span data-ttu-id="77bfd-110">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="77bfd-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="77bfd-111">**Identificador de error:** BC42104</span><span class="sxs-lookup"><span data-stu-id="77bfd-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="77bfd-112">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="77bfd-112">To correct this error</span></span>  
  
- <span data-ttu-id="77bfd-113">Compruebe la lógica del flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control pasa a cualquier instrucción que lo lee.</span><span class="sxs-lookup"><span data-stu-id="77bfd-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
- <span data-ttu-id="77bfd-114">Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="77bfd-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="77bfd-115">Consulte "Inicialización" en [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="77bfd-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77bfd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="77bfd-116">See also</span></span>

- [<span data-ttu-id="77bfd-117">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="77bfd-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="77bfd-118">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="77bfd-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="77bfd-119">Solución de problemas de variables</span><span class="sxs-lookup"><span data-stu-id="77bfd-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
