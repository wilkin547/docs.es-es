---
description: "Más información acerca de: BC42104: la variable ' <variablename> ' se usa antes de que se le haya asignado un valor"
title: La variable '<variablename>' se utiliza antes de ser asignada a un valor
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 501c3e3971c5ca0ebdba6981134f5029b77d0075
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701500"
---
# <a name="bc42104-variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="c7ef4-103">BC42104: la variable ' \<variablename> ' se usa antes de que se le haya asignado un valor</span><span class="sxs-lookup"><span data-stu-id="c7ef4-103">BC42104: Variable '\<variablename>' is used before it has been assigned a value</span></span>

<span data-ttu-id="c7ef4-104">La variable ' \<variablename> ' se usa antes de que se le haya asignado un valor.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-104">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="c7ef4-105">Podría producirse una excepción de referencia nula en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-105">A null reference exception could result at run time.</span></span>

 <span data-ttu-id="c7ef4-106">Una aplicación tiene al menos una ruta de acceso posible a través de su código que lee una variable antes de que se le asigne un valor.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-106">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>

 <span data-ttu-id="c7ef4-107">Si nunca se ha asignado un valor a una variable, contiene el valor predeterminado para su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-107">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="c7ef4-108">Para un tipo de datos de referencia, el valor predeterminado es [Nothing](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="c7ef4-108">For a reference data type, that default value is [Nothing](../nothing.md).</span></span> <span data-ttu-id="c7ef4-109">Leer una variable de referencia que tiene un valor de `Nothing` puede producir una excepción <xref:System.NullReferenceException> en algunas circunstancias.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-109">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>

 <span data-ttu-id="c7ef4-110">De forma predeterminada, este mensaje es una advertencia.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-110">By default, this message is a warning.</span></span> <span data-ttu-id="c7ef4-111">Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c7ef4-111">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="c7ef4-112">**Identificador de error:** BC42104</span><span class="sxs-lookup"><span data-stu-id="c7ef4-112">**Error ID:** BC42104</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c7ef4-113">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c7ef4-113">To correct this error</span></span>

- <span data-ttu-id="c7ef4-114">Compruebe la lógica del flujo de control y asegúrese de que la variable tiene un valor válido antes de que el control pase a cualquier instrucción que lo lea.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-114">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>

- <span data-ttu-id="c7ef4-115">Una manera de garantizar que la variable siempre tiene un valor válido es inicializarla como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="c7ef4-115">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="c7ef4-116">Vea "Initialization" en la [instrucción Dim](../statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c7ef4-116">See "Initialization" in [Dim Statement](../statements/dim-statement.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ef4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7ef4-117">See also</span></span>

- [<span data-ttu-id="c7ef4-118">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="c7ef4-118">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="c7ef4-119">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="c7ef4-119">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="c7ef4-120">Solución de problemas de variables</span><span class="sxs-lookup"><span data-stu-id="c7ef4-120">Troubleshooting Variables</span></span>](../../programming-guide/language-features/variables/troubleshooting-variables.md)
